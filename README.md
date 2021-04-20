# trySwiftColorKitProSource

Closed-source library for the try! Swift World conference

xcodebuild archive \
-scheme trySwiftColorKitPro \
-destination "generic/platform=iOS" \
-archivePath build/trySwiftColorKitPro-iOS \
SKIP_INSTALL=NO \
BUILD_LIBRARY_FOR_DISTRIBUTION=YES

xcodebuild archive \
-scheme trySwiftColorKitPro \
-destination "generic/platform=iOS Simulator" \
-archivePath build/trySwiftColorKitPro-iOSSim \
SKIP_INSTALL=NO \
BUILD_LIBRARY_FOR_DISTRIBUTION=YES

xcodebuild archive \
-scheme trySwiftColorKitPro \
-destination "generic/platform=OS X" \
-archivePath build/trySwiftColorKitPro-macOS \
SKIP_INSTALL=NO \
BUILD_LIBRARY_FOR_DISTRIBUTION=YES

xcodebuild -create-xcframework \
-framework build/trySwiftColorKitPro-iOS.xcarchive/Products/Library/Frameworks/trySwiftColorKitPro.framework \
-framework build/trySwiftColorKitPro-iOSSim.xcarchive/Products/Library/Frameworks/trySwiftColorKitPro.framework \
-framework build/trySwiftColorKitPro-macOS.xcarchive/Products/Library/Frameworks/trySwiftColorKitPro.framework \
-output build/trySwiftColorKitPro.xcframework
