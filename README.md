# rn-fontawesome
React Native Fontawesome Icons

# Benefits
- No bloatware, one package with one iconset, nothing more nothing less
- Full set of FontAwesome Icons properly updated
- Insanely fast with minimal memory footprint
- Uses the OS to render icons, for best in class performance (refer to performance note bellow)

# Installation process

## Using yarn
`npm i -g yarn`

`yarn add rn-fontawesome`

## Using npm
`npm i --save rn-fontawesome`

This module uses Font Awesome version [4.7.0](http://fontawesome.io/assets/font-awesome-4.7.0.zip). There is no need to link binaries just import the package and include the Font File
in your project.
* Extract font-awesome-4.7.0.zip
* copy ./font/fontawesome-webfont.ttf and paste to your assets folder of app /assets/font/
* edit package.json and add
  ```
  "rnpm": {
    "assets": [
      "./assets/fonts"
    ]
  }
  ```
* After that from open project directory from terminal and run
  ```
    react-native link rnpm
  ```
## Please restart your simulator otherwise you can face unknown fontFamily fontawesome error

# Usage
```javascript
import FontAwesome, { Icons } from 'rn-fontawesome';

...
render() {
  return (
    <View>
      <TouchableHighlight>
        <Text style={{margin: 10, fontSize: 15, textAlign: 'left'}}>
          <FontAwesome>{Icons.chevronLeft}</FontAwesome>
          Text
        </Text>
      </TouchableHighlight>
    </View>
  );
},
```

# Note on hyphens
Javascript don't accept hyphens as valid object names hence all hyphens were removed and
names converted to camel case.

Example: `th-large` becomes `thLarge`

# Styling
You can apply styles directly into the FontAwesome RN component by just passing a style as you do in a `<Text>` component.

```

<FontAwesome style={{fontSize: 32}}>
    {Icons.chevronLeft}
</FontAwesome>

```

# Why this is fast, and uses almost no extra memory
This package uses the Text element to render Icons. The Text element delegates
to the OS the render process of the icons based on the Font file.
Both IOS and Android render fonts amazingly fast with little memory overhead. In essence
FontAwesome.ttf will be used by the OS to render icons and will benefit of years
of native software improvement as well hardware acceleration.

## Forked from [react-native-fontawesome](https://github.com/entria/react-native-fontawesome)
