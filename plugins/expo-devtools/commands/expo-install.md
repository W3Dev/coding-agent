# /expo-install - Install Expo packages

Install packages using `npx expo install` for proper version compatibility.

## Usage

```
/expo-install <package-name> [additional-packages...]
```

## Examples

```
/expo-install expo-camera
/expo-install expo-notifications expo-device
/expo-install react-native-reanimated
/expo-install @react-navigation/native
```

## Behavior

1. Use the Expo MCP `add_library` tool to install packages
2. Ensures version compatibility with your Expo SDK version
3. Automatically installs peer dependencies
4. Updates package.json and installs node_modules

## Arguments

- `package-name` (required): The package to install
- `additional-packages` (optional): More packages to install in the same command

## Notes

- Uses `npx expo install` under the hood for proper versioning
- Recommended over `npm install` for Expo projects
