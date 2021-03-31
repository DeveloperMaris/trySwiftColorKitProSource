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
-archivePath build/trySwiftColorKitPro-iOS \
SKIP_INSTALL=NO \
BUILD_LIBRARY_FOR_DISTRIBUTION=YES
```

### Step 2 - Archive for iOS Simulator

```
xcodebuild archive \
-scheme trySwiftColorKitPro \
-destination "generic/platform=iOS Simulator" \
-archivePath build/trySwiftColorKitPro-sim \
SKIP_INSTALL=NO \
BUILD_LIBRARY_FOR_DISTRIBUTION=YES
```

### Step 3 - Archive for macOS

```
xcodebuild archive \
-scheme trySwiftColorKitPro \
-destination "generic/platform=OS X" \
-archivePath build/trySwiftColorKitPro-macOS \
SKIP_INSTALL=NO \
BUILD_LIBRARY_FOR_DISTRIBUTION=YES
```

### Step 4 - Create XCFramework

```
xcodebuild -create-xcframework \
-framework build/trySwiftColorKitPro-iOS.xcarchive/Products/Library/Frameworks/trySwiftColorKitPro.framework \
-framework build/trySwiftColorKitPro-sim.xcarchive/Products/Library/Frameworks/trySwiftColorKitPro.framework \
-framework build/trySwiftColorKitPro-macOS.xcarchive/Products/Library/Frameworks/trySwiftColorKitPro.framework \
-output build/trySwiftColorKitPro.xcframework
```

