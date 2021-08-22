# What's different?

- You don't just have your pick of HTML elements like you would in a standard web application: there are React Native core components that you have to use.

- On the same note, the CSS you can use is curtailed from standard CSS. Styling is based off of objects rather than stylesheets.

# Tooling

-To run RN on a Mac, you'll need a text-editor, Expo (including the Expo CLI), and Android Studio

# Setup 

- Run `expo init <ProjectName>`

# Components

- Component docs, from the React Native site: https://reactnative.dev/docs/intro-react-native-components

## Android Exclusive

- `DrawerLayoutAndroid` wraps the native Android drawer

- `TouchableNativeFeedback` makes views respond to touches better on Android' prefer the platform-agnostic `Pressable`


## iOS Exclusive

- `SafeAreaView` acts as a container w/padding to keep Views within a viewable area of the screen.

= `InputAccessoryView` enables customization of the keyboard input accessory.