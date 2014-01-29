# Tango

This is a version of Tangerine for IOS

This project is dependent upon [tangerine-pouch](http://github.com/chrisekelley/tangerine-pouch) webapp. Clone tangerine-pouch,
remove the www directory in this repository, and create a symbolic link named www to the tangerine-pouch project.
Since tangerine-pouch is generated from the tangerine-pouch branch of [Tangerine](http://github.com/chrisekelley/tangerine-pouch),
it would make even more sense to check that out first, get it to render tangerine-pouch, and pat yourself on the back.

## Building

This app was bootstrapped using [Generator-cordova](https://github.com/dangeross/generator-cordova). I manually updated
the cordova version to 3.0 - see [issue 8](https://github.com/dangeross/generator-cordova/issues/8).

    grunt emulate --platform=ios --family=ipad

## clearing the database

IOS emulator [uses](http://caniuse.com/#feat=sql-storage) the Web SQL database, [which cannot be deleted](http://stackoverflow.com/a/7183114).
One way to clear it is to go to /Users/chrisk/Library/Application\ Support/iPhone\ Simulator/7.0.3/Applications
in the Finder. You'll see a list of folders with UUID's as names (e.g. 8C7ED6C7-83EA-48F2-A7C8-A06E88644263).
If you sort by date the most recent one is probably the one you want. To confirm, check if it has the Tangerine app in it.
Then navigate to Library/WebKit/LocalStorage/ and delete the file and folder that being with "file_."

## IOS Limitations

### Web SQL

Since IOS does not support IndexedDB, you're stuck with Web SQL. 

### 50 MB size limitation

There is a 50 MB size limitation enforced, so be careful about db size.

### Potential Issues with IOS7

There are some issues with using Web SQL database in IOS7 - see the Web SQL section in this [article](http://www.mobilexweb.com/blog/safari-ios7-html5-problems-apis-review). Although you can increase memory storage allocated to the database,
More information: [Increase memory popup event on IOS](https://bitbucket.org/ytkyaw/ydn-db/issue/76/increase-memory-popup-event-on-ios).
Potential solution: [15 second setInterval after fail](http://stackoverflow.com/questions/19126034/web-sql-grow-database-for-ios).


