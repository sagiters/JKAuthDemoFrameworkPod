# JKAuthDemoFrameworkPod

[![CI Status](https://img.shields.io/travis/sagiters19@gmail.com/JKAuthDemoFrameworkPod.svg?style=flat)](https://travis-ci.org/sagiters19@gmail.com/JKAuthDemoFrameworkPod)
[![Version](https://img.shields.io/cocoapods/v/JKAuthDemoFrameworkPod.svg?style=flat)](https://cocoapods.org/pods/JKAuthDemoFrameworkPod)
[![License](https://img.shields.io/cocoapods/l/JKAuthDemoFrameworkPod.svg?style=flat)](https://cocoapods.org/pods/JKAuthDemoFrameworkPod)
[![Platform](https://img.shields.io/cocoapods/p/JKAuthDemoFrameworkPod.svg?style=flat)](https://cocoapods.org/pods/JKAuthDemoFrameworkPod)

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Requirements

## Installation

JKAuthDemoFrameworkPod is available through [CocoaPods](https://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'JKAuthDemoFrameworkPod'
```

## Configure Your Project

```ruby
<key>LSApplicationQueriesSchemes</key>
<array>
  <string>jkos</string>
</array>
<key>JKOClientID</key>
<string>JKOS-ID</string>
<key>CFBundleURLTypes</key>
<array>
  <dict>
    <key>CFBundleURLSchemes</key>
    <array>
      <string>JKOS-ID</string>
    </array>
  </dict>
</array>
```

## Author

sagiters19@gmail.com, sagiters19@gmail.com

## License

JKAuthDemoFrameworkPod is available under the MIT license. See the LICENSE file for more info.
