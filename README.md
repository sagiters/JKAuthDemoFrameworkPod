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

## Connect the App Delegate

以下列程式碼取代 AppDelegate 方法中的程式碼。此程式碼會在應用程式啟動時初始化 SDK

```ruby=
//
//  AppDelegate.swift
//

import UIKit
import JKOAuth

@main
class AppDelegate: UIResponder, UIApplicationDelegate {

    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        // Override point for customization after application launch.

        JKOAuthService.shared.application(application, didFinishLaunchingWithOptions: launchOptions)

        return true
    }
    
    func application(_ app: UIApplication, open url: URL, options: [UIApplication.OpenURLOptionsKey : Any] = [:]) -> Bool {

        JKOAuthService.shared.application(app, open: url, sourceApplication: options[UIApplication.OpenURLOptionsKey.sourceApplication] as? String, annotation: options[UIApplication.OpenURLOptionsKey.annotation])
    }
}
```

## 

iOS 13 已將開啟網址功能移至 SceneDelegate。如果您使用的是 iOS 13，請將下列方法新增至 SceneDelegate，這樣登入或分享等操作才能正常運作：

```ruby=
//
//  SceneDelegate.swift
//

import UIKit
import JKOAuth

class SceneDelegate: UIResponder, UIWindowSceneDelegate {
...

    func scene(_ scene: UIScene, openURLContexts URLContexts: Set<UIOpenURLContext>) {
        guard let urlContext = URLContexts.first else { return }
        JKOAuthService.shared.application(UIApplication.shared, open: urlContext.url, sourceApplication: urlContext.options.sourceApplication, annotation: urlContext.options.annotation)
    }

}
```


## Author

sagiters19@gmail.com, sagiters19@gmail.com

## License

JKAuthDemoFrameworkPod is available under the MIT license. See the LICENSE file for more info.
