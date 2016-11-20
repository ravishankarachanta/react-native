# react-native-packetzoom [![npm version](https://img.shields.io/npm/v/react-native-packetzoom.svg?style=flat)](https://www.npmjs.com/package/react-native-packetzoom)

# Accelerate your react native app performance without rewriting networking code

React Native PacketZoom SDK for iOS + Android

![](http://i.imgur.com/GPEgdkT.png)


# Intro

At __PacketZoom__ we designed a modern, UDP-based network protocol with mobile apps in mind. This enables faster downloads, reduced latency, efficient and reliable data transfers between your app and the cloud. In addition to speed, one of the advantages of PacketZoom is that it handles seamless transition between networks without interrupting ongoing sessions. This is a unique advantage of the PacketZoom protocol over HTTP/TCP stack in common use today. 

Today we're redefining how networking works for React Native apps, empowering them with PacketZoom SDK and our [worldclass cluster of servers](http://status.packetzoom.com).

# Installation

First, download the library from npm:

```
npm install react-native-packetzoom@latest --save
```

Then you must install the native dependencies: You can use `rnpm` (now part of `react-native` core) to
add native dependencies automatically then continue the directions below depending on your target OS.

   `$ react-native link`
   
React Native versions from 0.30 and above should work out of the box, we cannot guarantee that earlier than 0.30
will have smooth integration experience, it may require additional manual steps like `rnpm` for example.

## Javascript

Sign up for free __PacketZoom__ account here: https://packetzoom.com/developers.html to get credentials for your app.

Add these two lines of code where you initialize your main component

```js

import Packetzoom from 'react-native-packetzoom'

Packetzoom.init('packetzoom-app-id', 'packetzoom-api-key')
```

As you may already know the XMLHttpRequest API is built in to React Native. This means that you can use third party libraries such as [Frisbee](https://github.com/crocodilejs/frisbee), [Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) or [Axios](https://github.com/mzabriskie/axios) that depend on it. Ultimately XMLHttpRequest API is implemented using native [NSURLSession API](https://developer.apple.com/library/content/documentation/Cocoa/Conceptual/URLLoadingSystem/Articles/UsingNSURLSession.html#//apple_ref/doc/uid/TP40013509-SW1) on iOS side and [OkHttp3](https://github.com/square/okhttp) on Android
where PacketZoom SDK will eventually intercept them.

From now on all your [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API),
[Axios](https://github.com/mzabriskie/axios) or [Apisauce](https://github.com/skellock/apisauce) requests will be accelerated
by __PacketZoom__. You can access all [network analytics](https://packetzoom.com/blog/introducing-http-optimizer-and-analytics-service.html) data on web dashboard when you login under your account.

## iOS

Drag PZSpeed.Framework from RNPacketZoom.xcodeproj to your app frameworks folder like shown bellow:

![](http://i.imgur.com/z71C8Nh.png)


Make sure you linking against it in Build Phases -> Link Binary with Libraries section

![](http://i.imgur.com/e6ftLfX.png)

Also make sure that the following frameworks and libraries are part of your project: 

- CoreLocation.framework
- SystemConfiguration.framework
- CoreTelephony.framework
- Foundation.framework
- libz.tbd
- libc++.tbd

## Android

No additional changes required for Android


[Join The Rebellion](https://packetzoom.com/developers.html) and experience request speedups and uninterrupted network connections across all mobile and wifi networks
