# trySwiftColorKitProSource

Closed-source library for the try! Swift World conference

## How to create an XCFramework

To create an XCFramework, we need to archive the framework for iOS,
iOS simulator and macOS, then gather them all in a single XCFramework.


### Step 1 - Archive for iOS

```
xcodebuild archive \
-scheme trySwiftColorKitPro \
-destination "generic/platform=iOS" \
-archivePath build/trySwiftColorKitPro \
SKIP_INSTALL=NO \
BUILD_LIBRARY_FOR_DISTRIBUTION=YES
```

### Step 2 - Archive for iOS Simulator

```
xcodebuild archive \
-scheme trySwiftColorKitPro \
-destination "generic/platform=iOS Simulator" \
-archivePath build/trySwiftColorKitPro-Sim \
SKIP_INSTALL=NO \
BUILD_LIBRARY_FOR_DISTRIBUTION=YES
```
