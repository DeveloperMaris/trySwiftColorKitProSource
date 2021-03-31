# trySwiftColorKitProSource

Closed-source library for the try! Swift World conference

## How to create an XCFramework

To create an XCFramework, we need to archive the framework for iOS,
iOS simulator and macOS, then gather them all in a single XCFramework.


### Step 1 - Create an iOS archive:

```
xcodebuild archive \
-scheme trySwiftColorKitPro \
-destination "generic/platform=iOS" \
-archivePath build/trySwiftColorKitPro \
SKIP_INSTALL=NO \
BUILD_LIBRARY_FOR_DISTRIBUTION=YES
```
