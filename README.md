SwiftTryCatch
=============

Adds try/catch support for Swift.

Simple wrapper built around Objective-C `@try`/`@catch`/`@finally`.

**Note:** This repository was originally forked from [https://github.com/williamFalcon/SwiftTryCatch](https://github.com/williamFalcon/SwiftTryCatch) and updated to work with Swift 2.0, since the original API conflicted with new try/catch keywords introduced by new Swift version.

##Usage

### Install via Swift Package Manager

To use this specific repository version of SwiftTryCatch add it to your Package.swift manifest.

```swift
import PackageDescription

let package = Package(
    name: "YourModule",
    dependencies: [
        .Package(url: "https://github.com/sjpickup/SwiftTryCatch.git", majorVersion: 1, minor: 1),
    ]
)
```

### Install via CocoaPods

To use this specific repository version of SwiftTryCatch use the following pod definition:

```ruby
pod 'SwiftTryCatch', :git => 'https://github.com/sjpickup/SwiftTryCatch.git'
```

This will use the podspec from this forked repository with the API signature changes.

### Create bridging header

- When prompted with "Would you like to configure an Obj-C bridging header?", press "Yes".
- Go to bridging header and add:

```objc
#import "SwiftTryCatch.h"
```

### Use

```swift
SwiftTryCatch.tryBlock({
        // try something
    }, catchBlock: { (error) in
        println("\(error.description)")
    }, finallyBlock: {
        // close resources
    })
```
