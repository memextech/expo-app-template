# Web & Mobile Expo App

## Project Overview
TODO

## Project Structure
TODO

## Memex Universe
The `.memex` directory is used by the Memex universe, a template system for project management. The `config.yaml` file stores metadata about the project, while `rules.md` (this file) provides instructions and documentation for working with this project. These files are used by the Memex agent to guide development and iteration on the project.

## Prerequisites
- Expo account (Person needs to register with [Expo](https://expo.dev/))
- Node.js 18.0+ (LTS recommended)
- npm or yarn
- Xcode for iOS development
- Android Studio for Android development

## Setup Instructions

1. Clone this repository
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

## Generic information how to setup Expo and create and configure new projects

#### Install Expo CLI
```bash
npm install -g expo-cli
```

#### Login to Expo
```bash
npx expo login
```

#### Create a New Expo Project with file-based routing with Expo Router and TypeScript enabled
```bash
npx create-expo-app@latest your-app-name --template tabs
```

#### Start the application
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
