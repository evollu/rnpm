:iphone: rnpm <img src="https://david-dm.org/rnpm/rnpm.svg" />
=============

**React Native Package Manager** built to ease your daily React Native development. Inspired by `Cocoapods`, `fastlane` and `react-native link` it acts as your best friend and guides you through the native unknowns. It aims to work with almost all packages available with no extra configuration required.

**This version is still in alpha as we are getting unit tests written. Feel free to submit bugs and feature requests. Always use this tool in a connection with source control to make sure all changes can be reverted.**

## Requirements

- node >= 4.x

## Getting started

**Installation**
```bash
$ npm install rnpm -g
```

**Running**
From your's project folder install some react-native modules that require additional installation and simply run:
```bash
$ rnpm link
```
In the case you want to link only one depepndency, you can specify it's name as an argument:
```bash
$ rnpm link react-native-blur
```

## Rationale

Why? Tooling is important. We all know this. One of the biggest advantages of native iOS development is XCode and its great tools. Unfortunately, the process of adding native dependencies to React Native projects is far from perfect and our aim is to make it fun again.

React Native Package Manager provides you with (soon) multiple actions to help you with daily development, including automatic app store releases, over-the-air integration with AppHub and react-native-playground shares.

**But hey, we are tired of tools and 1239012 .rc files**

So are we. That's why we have spent great amount of work on getting configuration done right. Our packager automatically scans your source directory and dependencies you are working with. This approach allows it to link all the things without supplying any extra configuration. It detects Android package names, import paths, gradle location - and for iOS - it works with any code structure you have ever came up with.

And don't worry - in case it fails, you can always add `rnpm` object to your `package.json` - our `npm` in a name is not a mistake! We embrance existing ecosystem and integrate with the present tooling for maxium developer experience.

## Available commands

#### rnpm link [name]
Automatically updates your project by linking all dependencies for Android (if present) and for iOS (if present). It's a great fit to your `postinstall` hook to always make sure you are linked. You can supply optional [name] argument to link only one dependency, e.g.

```bash
$ rnpm link react-native-module
```

## Advanced usage
If you're authoring an awesome react-native library with custom assets, you probably need an additional step after linking - copying assets to the application folder. Well, that's not complicated: just add `rnpm` section in your `package.json` file:
```json
...
"rnpm": {
  "assets": ["Fonts"]
},
...
```
We'll copy your assets carefully with love :heart:

## Roadmap

We have lots of plans to make this tool better, some of them are:
- [ ] 100% test coverage
- [ ] support for plugins and custom project linters
- [ ] rnpm ship appstore
- [ ] rnpm ship apphub
- [ ] rnpm ship hockey
- [ ] rnpm build
- [ ] rnpm share rnplay
- [ ] your ideas

## FAQ

#### How's that different from react-native link

react-native link is great, but it only works for Android now. It also does not automatically add packages to your project nor support custom folder configuration. We aim to solve these issues by analyzing folders and getting maxium informations available from them. When running `rnpm link` you don't have to think about the package exported by developer or the import path to include in your Java project.

#### Does it work with Cocoapods?

Yes, in fact - it has nothing to do with it. What it does is just linking static libraries automatically to your xcodeproj in the normal way you have been doing that. There are no more other changes.

## Special thanks

Special thanks to [**coreh**](https://github.com/coreh) for giving us the `rnpm` name in the registry.

## Versioning

This project follows semver. There are several 0.x versions published to npm registry you should not install as they belong to the previous project that was using that name 2 years ago.

## Contributing

We welcome all contributors, simply make an issue or send over a pull request. We really appreciate your help - let's build this tool together!

## Sponsors

This tool development and maintainance is sponsored by below companies:

<a href="http://manandmoon.com" title="Man+Moon"><img src="http://manandmoon.com/images/man-moon-full-logo-.svg" width="200" /></a>

## License

The MIT License (MIT)

Copyright (c) 2015 Mike Grabowski, 2015 Alexey Kureev

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
