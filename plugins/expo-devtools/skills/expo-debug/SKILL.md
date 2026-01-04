# Expo Debug Skill

Use this skill when working on Expo/React Native applications to debug issues, access documentation, and interact with running apps.

## When to Use

- User is building a React Native app with Expo
- User needs help with Expo-specific APIs or configuration
- User wants to install or configure Expo packages
- User needs to debug mobile app issues
- User asks about EAS Build, Updates, or Submit
- User needs to test UI components visually

## Instructions

### For Documentation Lookup

1. Use the Expo MCP `learn` tool to access official documentation
2. Use `search_documentation` for natural language queries
3. Supplement with Context7 for React Native or third-party library docs
4. Use Grep to find real-world code examples

### For Package Installation

1. Use the Expo MCP `add_library` tool
2. Ensure version compatibility with the current Expo SDK
3. Check for required configuration (app.json, plugins, etc.)

### For Visual Testing (requires local dev server)

1. First, ensure dev server is running with MCP enabled
2. Use `automation_take_screenshot` to capture current screen
3. Use `automation_tap_by_testid` to interact with UI elements
4. Use `automation_find_view_by_testid` to query component properties

### For Project Configuration

1. Use `generate_agents_md` to create AI configuration files
2. Check app.json/app.config.js for configuration issues
3. Review EAS configuration for build/submit issues

## Available MCP Tools

### Expo MCP (Remote - requires EAS paid plan)
- `learn` - Access Expo documentation
- `search_documentation` - Natural language doc search
- `add_library` - Install packages via npx expo install

### Expo MCP (Local - requires dev server)
- `automation_take_screenshot` - Capture simulator screen
- `automation_tap_by_testid` - Tap UI elements
- `automation_find_view_by_testid` - Query component properties
- `open_devtools` - Launch React Native DevTools
- `expo_router_sitemap` - Display routing structure

### Shared Tools
- `mcp__context7__query-docs` - Library documentation
- `mcp__deepwiki__ask_question` - GitHub repo questions
- `mcp__grep__searchGitHub` - Real-world code examples

## Example Workflow

When user says: "How do I add push notifications to my Expo app?"

1. Search docs: `expo.search_documentation("push notifications setup")`
2. Get detailed guide: `expo.learn("expo-notifications")`
3. Install package: `expo.add_library("expo-notifications")`
4. Find examples: `grep.searchGitHub("expo-notifications", language=["TypeScript"])`
5. Provide step-by-step implementation guide
