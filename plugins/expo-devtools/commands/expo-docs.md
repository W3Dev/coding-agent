# /expo-docs - Look up Expo documentation

Access Expo documentation and learn about React Native development with Expo.

## Usage

```
/expo-docs <topic> [query]
```

## Examples

```
/expo-docs navigation
/expo-docs push-notifications setup
/expo-docs eas build configuration
/expo-docs camera permissions
```

## Behavior

1. Use the Expo MCP `learn` tool to access documentation
2. Use `search_documentation` for natural language queries
3. Return relevant documentation with code examples
4. Supplement with Context7 for additional library docs if needed

## Arguments

- `topic` (required): The Expo/React Native topic to look up
- `query` (optional): Specific question or subtopic to search for

## Notes

- Requires EAS paid plan for full Expo MCP functionality
- Works best with Expo SDK 54+
