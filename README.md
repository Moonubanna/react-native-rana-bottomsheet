# rn-bottom-test

Cross platform scrollable bottom sheet with virtualisation support and fully native animations!!

<!-- | ![](media/bottom1.gif)|
| :--------------------:| -->

## Installation

Open a Terminal in the project root and run:

```sh
yarn add rn-bottom-test
```

or if you use `npm`:

```sh
npm install rn-bottom-test
```

If you are using Expo, you are done.

Install and link [react-native-gesture-handler](https://kmagiera.github.io/react-native-gesture-handler/docs/getting-started.html) and [react-native-reanimated](https://github.com/kmagiera/react-native-reanimated).

## Usage

```javascript
import { Dimensions, Platform } from 'react-native'
import BottomSheet from 'rn-bottom-test';
const refBottom = React.useRef();
const HEIGHT = Dimensions.get('screen').height

class Example extends React.Component {
  render() {
    return (
      <View style={{flex: 1}}>
        <BottomSheet 
        isOpen
        ref={refBottom}
        sliderMaxHeight={HEIGHT - 100}
        >
        {(onScrollEndDrag) => (
          <ScrollView onScrollEndDrag={onScrollEndDrag}>
            {[...Array(20)].map((_, index) => (
              <View key={`${index}`} style={styles.itemStyle}>
                <Text>{`Item number: ${index + 1}`}</Text>
              </View>
            ))}
          </ScrollView>
        )}
        </BottomSheet>
      </View>
    );
  }
}
```

## Props

| name                         | required | default   | description                                                                                                                                                                                                                                                                    |
| ---------------------------- | -------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| children              | yes       | <View />         | A component or a render function. Use toggleSlider function instead 
| isOpen              | no       | true         | Initial state of the panel; true to render it opened, false otherwise. Important: Do not try to open/close the panel througth this prop, see togglePanel method instead                                                                                                                    
| sliderMinHeight              | no       | 50         | Min height of the panel
| sliderMaxHeight              | no       | Dimensions.get('window').height * 0.5         | Max height of the panel
| animation              | no       | Easing.quad         | The close/open animation of the panel
| onOpen              | no       | () => null        | Function to execute when the panel is opened
| onClose              | no       | () => null        | Function to execute when the panel is closed
| initialPosition              | no       | 0         | Determines initial position point of bottom sheet. The value outside of snap points. 

## Contributors ✨

Thanks goes to these wonderful people:

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/Moonubanna"><img src="https://avatars.githubusercontent.com/u/17289834?v=4" width="100px;" alt="Praveen singh"/><br /><sub><b>Numan</b></sub></a><br /><a href="#infra-Numan" title="Infrastructure (Hosting, Build-Tools, etc)">🚇</a> <a href="https://github.com/Moonubanna" title="Code">💻</a></td>
  </tr>
</table>

<!-- ALL-CONTRIBUTORS-LIST:END -->
