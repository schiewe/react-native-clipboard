# @react-native-community/clipboard

[![Build Status][build-badge]][build]
[![Version][version-badge]][package]
![Supports iOS and Android][support-badge]
[![MIT License][license-badge]][license]
[![Lean Core Badge][lean-core-badge]][lean-core-issue]


React Native Clipboard API for both iOS and Android

| iOS | Android |
| --- | --- |
| <img src ="https://user-images.githubusercontent.com/6936373/73284520-0ce29880-4238-11ea-9d0e-2061b2d6f17a.png" width="320"/> | <img src ="https://user-images.githubusercontent.com/6936373/73284517-0ce29880-4238-11ea-96c7-5a6337c43da5.png" width="320"/> |



## Getting started
Install the library using either Yarn:

```
yarn add @react-native-community/clipboard
```

or npm:

```
npm install --save @react-native-community/clipboard
```

## Link

- React Native v0.60+

For iOS, use `cocoapods` to link the package.

run the following command:

```
$ cd ios && pod install
```

For android, the package will be linked automatically on build.

- React Native <= 0.59

run the following command to link the package:

```
$ react-native link @react-native-community/clipboard
```

or you could follow the instructions to [manually link the project](https://facebook.github.io/react-native/docs/linking-libraries-ios#manual-linking)

## Upgrading to React Native 0.60+

New React Native comes with `autolinking` feature, which automatically links Native Modules in your project. In order to get it to work, make sure you unlink `Clipboard` first:

```
$ react-native unlink @react-native-community/clipboard
```

## Migrating from the core `react-native` module
This module was created when the NetInfo was split out from the core of React Native. To migrate to this module you need to follow the installation instructions above and then change you imports from:

```javascript
import { Clipboard } from "react-native";
```

to:

```javascript
import Clipboard from "@react-native-community/clipboard";
```

## Usage
Start by importing the library:

```javascript
import Clipboard from "@react-native-community/clipboard";

type Props = $ReadOnly<{||}>;
type State = {|
  clipboardContent: string,
|};

export default class App extends React.Component<Props, State> {
  state = {
    clipboardContent: 'The state variable which contains Clipboard Content',
  };

  readFromClipboard = async () => {
    const content = await Clipboard.getString();
    this.setState({clipboardContent: content});
  };

  writeToClipboard = async () => {
    Clipboard.setString(this.state.text);
    alert('Copied to clipboard');
  };
}
```

## Maintainers

* [M.Haris Baig](https://github.com/harisbaig100)
* [Jesse Katsumata](https://github.com/Naturalclar)

## Contributing

Please see the [`contributing guide`](/CONTRIBUTING.md).

## License

The library is released under the MIT licence. For more information see [`LICENSE`](/LICENSE).

[build-badge]: https://img.shields.io/circleci/project/github/react-native-community/react-native-clipboard/master.svg?style=flat-square
[build]: https://circleci.com/gh/react-native-community/react-native-clipboard
[version-badge]: https://img.shields.io/npm/v/@react-native-community/clipboard.svg?style=flat-square
[package]: https://www.npmjs.com/package/@react-native-community/clipboard
[support-badge]:https://img.shields.io/badge/platforms-android%20|%20ios-lightgrey.svg?style=flat-square
[license-badge]: https://img.shields.io/npm/l/@react-native-community/clipboard.svg?style=flat-square
[license]: https://opensource.org/licenses/MIT
[lean-core-badge]: https://img.shields.io/badge/Lean%20Core-Extracted-brightgreen.svg?style=flat-square
[lean-core-issue]: https://github.com/facebook/react-native/issues/23313
