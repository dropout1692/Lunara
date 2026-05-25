# Lunara Project Structure

This is a multi-module project with the following structure:

## Modules

### 1. **lunara-backend**
- **Type**: Spring Boot REST API
- **Language**: Java
- **Build Tool**: Gradle
- **Purpose**: Backend API server for the Lunara application
- **Location**: `/lunara-backend`
- **Key Files**:
  - `build.gradle` - Spring Boot and dependency configuration
  - `src/main/java/wtf/dpt/lunarabackend/` - Java source code
  - `src/main/resources/application.properties` - Application configuration

### 2. **lunara-web**
- **Type**: Web UI Application
- **Language**: JavaScript/React
- **Build Tool**: npm
- **Purpose**: Web-based user interface
- **Location**: `/lunara-web`
- **Key Files**:
  - `package.json` - Dependencies and scripts
  - `src/App.jsx` - Main React component
  - `src/index.jsx` - React entry point
  - `public/index.html` - HTML template

### 3. **lunara-mobile**
- **Type**: Mobile Application
- **Language**: JavaScript/React Native
- **Build Tool**: npm / Expo
- **Purpose**: iOS and Android mobile application
- **Location**: `/lunara-mobile`
- **Key Files**:
  - `package.json` - Dependencies and scripts
  - `app.json` - Expo configuration
  - `app/_layout.jsx` - Navigation setup
  - `app/index.jsx` - Home screen

## Building the Project

### Build All Modules
From the root `Lunara` directory:
```bash
./gradlew build
```

This will build the `lunara-backend` module automatically.

### Build Individual Modules

#### Backend
```bash
cd lunara-backend
./gradlew build
```

#### Web UI
```bash
cd lunara-web
npm install
npm start    # Development server
npm run build # Production build
```

#### Mobile
```bash
cd lunara-mobile
npm install
npm start        # Start Expo development server
npm run android  # Run on Android
npm run ios      # Run on iOS
npm run web      # Run on web
```

## API Communication

All modules communicate with the Spring Boot backend (`lunara-backend`) via REST APIs.

- **Web UI**: Uses axios or fetch to call backend APIs
- **Mobile App**: Uses axios or react-native HTTP client to call backend APIs

## Development Setup

1. **Backend**: Java 25+ and Gradle
2. **Web**: Node.js 16+, npm or yarn
3. **Mobile**: Node.js 16+, Expo CLI, Android Studio (for Android), Xcode (for iOS)

## Configuration

Each module has its own configuration:
- Backend: `lunara-backend/src/main/resources/application.properties`
- Web: Environment variables or `.env` file
- Mobile: `app.json` and environment variables

