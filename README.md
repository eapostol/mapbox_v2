# React Native with the MapBox Maps SDK for iOS and Android

This repository is a rebuild of part of the work I did evaluating React Native for use in the 2nd generation Intelex Eversync App. In this case using a third-party library to use mapping functionality (at the time, Google Maps implementation was in its early stages).

## What is Mapbox?

Mapbox is the location data platform for mobile and web applications. It provides [building blocks](https://www.mapbox.com/products/) to add location features like maps, search, and navigation into any experience needed. It has a straightforward set of APIs, SDKs and open source libraries for interactivity and control. It is required to set up an account with Mapbox .


##  Notes:

I wasn't able to install react-native-mapbox using npm due to permission
issues. I instead installed it using Yarn. It was based on this scenario:

- homebrew controls node and npm
- node version manager (nvm) controls active version of node
- used node 9.5.0 to create template react-native project in webstorm
- using npm install @mapbox/react-native-mapbox-gl --save resulted in an installation error ; react-native was already created from the template project in webstorm, and I am assuming that the npm install for mapbox was attempting to install a react dependency.

Issues:

`CoreData: annotation:  Failed to load optimized model at path '/Applications/Xcode.app/Contents/Applications/Instruments.app/Contents/Frameworks/InstrumentsPackaging.framework/Versions/A/Resources/XRPackageModel.momd/XRPackageModel 9.0.omo'`

https://stackoverflow.com/questions/46463536/coredata-annotation-failed-to-load-optimized-model-react-native

on first build

`The following commands produced analyzer issues:
	Analyze Base/RCTModuleMethod.mm
	Analyze Modules/RCTUIManager.m
(2 commands with analyzer issues)`

https://github.com/facebook/react-native/issues/12609

on subsequent refreshes -

`Loading dependency graph...watchman warning:  Recrawled this watch 1 times, most recently because:
/Users/edward/Documents/projects-2018/ReactNative_projects/mapbox_v2: kFSEventStreamEventFlagUserDropped
To resolve, please review the information on`

https://facebook.github.io/watchman/docs/troubleshooting.html#recrawl

`To clear this warning, run:
watchman watch-del /Users/edward/Documents/projects-2018/ReactNative_projects/mapbox_v2 ; watchman watch-project /Users/edward/Documents/projects-2018/ReactNative_projects/mapbox_v2`