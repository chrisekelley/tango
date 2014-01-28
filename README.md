# Tango

This is a version of Tangerine for IOS

This project is dependent upon [tangerine-pouch](http://github.com/chrisekelley/tangerine-pouch) webapp. Clone tangerine-pouch,
remove the www directory in this repository, and create a symbolic link named www to the tangerine-pouch project.
Since tangerine-pouch is generated from the tangerine-pouch branch of [Tangerine](http://github.com/chrisekelley/tangerine-pouch),
it would make even more sense to check that out first, get it to render tangerine-pouch, and pat yourself on the back.

Building

    grunt emulate --platform=ios --family=ipad

This app was bootstrapped using [Generator-cordova](https://github.com/dangeross/generator-cordova). I manually updated
the cordova version to 3.0 - see [issue 8](https://github.com/dangeross/generator-cordova/issues/8) 

