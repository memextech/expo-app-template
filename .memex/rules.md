# Web & Mobile Expo App Documentation

## Project Overview
This is a template for building cross-platform mobile and web applications using Expo and React Native. The project is set up with Expo Router for file-based navigation, TypeScript for type safety, and includes a tab-based navigation structure. It provides a foundation for developing applications that can run on iOS, Android, and web platforms from a single codebase.

## Project Structure
- `/app`: Contains the application screens and navigation structure using Expo Router
  - `/(tabs)`: Tab-based navigation screens (index.tsx and two.tsx)
  - `_layout.tsx`: Root layout configuration
  - `+html.tsx`: HTML template for web platform
  - `+not-found.tsx`: 404 page
  - `modal.tsx`: Modal screen example
- `/components`: Reusable UI components
  - `EditScreenInfo.tsx`: Example component with screen information
  - `ExternalLink.tsx`: Component for external links
  - `StyledText.tsx`: Text styling component
  - `Themed.tsx`: Theme-aware components
  - Various hooks for client-only values and color schemes
- `/assets`: Static assets like images and fonts
- `/constants`: Application constants including colors and dimensions
- `/data`: Data storage and management

## Memex Universe
The `.memex` directory is used by the Memex universe, a template system for project management. The `config.yaml` file stores metadata about the project, while `rules.md` (this file) provides instructions and documentation for working with this project. These files are used by the Memex agent to guide development and iteration on the project.

## Prerequisites
- Expo account (Person needs to register with [Expo](https://expo.dev/))
- Node.js 18.0+ (LTS recommended)
- npm or yarn
- Xcode for iOS development
- Android Studio for Android development

## Setup Instructions

1. This is a template created using this command. DO NOT CREATE A NEW EXPO PROJECT.
```bash
npx create-expo-app@latest your-app-name --template tabs
```
2. Install Expo CLI if not available
```bash
npm install -g expo-cli
```
3. Ask user to login to expo and run this command line manually
```bash
npx expo login
```
4. Install dependencies:
```bash
npm install
```
5. Run the development server:
```bash
npm run start
```

### If any problems with compilation try these fixes

1. Fix tsconfig.json

```
"compilerOptions": {
 ...
    "jsx": "react-native",
 ...
```

2. Create babel.config.js

```
module.exports = function (api) {
  api.cache(true);
  return {
    presets: ['babel-preset-expo'],
    plugins: [
      [
        'module-resolver',
        {
          root: ['.'],
          alias: {
            '@': '.',
          },
        },
      ],
    ],
  };
}; 
```

3. Install babel-plugin-module-resolver package
```bash
npm install --save-dev babel-plugin-module-resolver
```

4. Clear the Metro bundler cache
```bash
npx expo start -c
```
