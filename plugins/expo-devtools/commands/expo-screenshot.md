# /expo-screenshot - Take app screenshot

Capture a screenshot of your running Expo app in the simulator/emulator.

## Usage

```
/expo-screenshot [--testid=<test-id>]
```

## Examples

```
/expo-screenshot
/expo-screenshot --testid=home-screen
/expo-screenshot --testid=login-button
```

## Behavior

1. Connect to the running Expo dev server
2. Use `automation_take_screenshot` to capture the current screen
3. Optionally navigate to a specific element by testID first
4. Return the screenshot for visual verification

## Requirements

- Expo dev server must be running with MCP enabled:
  ```bash
  EXPO_UNSTABLE_MCP_SERVER=1 npx expo start
  ```
- Simulator/emulator must be running with the app

## Arguments

- `--testid` (optional): Test ID of element to focus on before screenshot

## Notes

- This is a local tool requiring the dev server to be running
- Useful for visual verification during development
- Part of Expo's automation capabilities
