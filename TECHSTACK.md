# UrbanEye - Technology Stack Documentation

## 📱 Overview
UrbanEye is a cross-platform mobile and web application built with **Flutter** and powered by **Google Cloud services** for backend infrastructure and authentication.

---

## 🏗️ Architecture Stack

### **Frontend Framework**
- **Flutter** (v3.7.2+)
  - Cross-platform development for iOS, Android, Web, Windows, macOS, and Linux
  - Material Design UI components
  - Dart programming language

### **Backend & Cloud Services**
- **Google Firebase** - Core backend infrastructure
- **Google Cloud Firestore** - Real-time NoSQL database
- **Google Cloud Functions** - Serverless compute for backend logic
- **Firebase Authentication** - User authentication and authorization

---

## 📚 Dependencies & Libraries

### **Google Technologies** 🔵

#### **Firebase Suite**
1. **firebase_core** (v3.15.1)
   - Foundation package for all Firebase services
   - Initializes Firebase across all platforms

2. **firebase_auth** (v5.6.2)
   - User authentication and session management
   - Multi-factor authentication support
   - Google Sign-in integration

3. **cloud_firestore** (v5.6.11)
   - Real-time NoSQL database
   - Data synchronization across devices
   - Offline support with local caching

4. **cloud_functions** (v5.6.1)
   - Serverless backend functions
   - Triggered operations and API endpoints
   - Automatic scaling

5. **google_sign_in** (v7.1.0)
   - Native Google Sign-in integration
   - OAuth 2.0 authentication
   - Supports Web, Android, and iOS platforms

#### **Google UI & Fonts**
6. **google_fonts** (v6.2.1)
   - Access to Google Fonts library
   - Easy typography management
   - 1400+ font families

---

## 🎨 Additional Dependencies

### **UI & Animation**
- **flutter_animate** (v4.5.2) - Advanced animation framework
- **cupertino_icons** (v1.0.8) - iOS-style icons
- **Material Design Icons** - Built-in Material Design icons

### **Image & Media**
- **image_picker** (v1.1.2) - Image/media selection from device

### **Networking & HTTP**
- **http** (v1.4.0) - HTTP client for API calls

### **Development Tools**
- **flutter_lints** (v5.0.0) - Code quality and linting rules

---

## 📱 Platform-Specific Details

### **Android Development**
- **Gradle build system** with Kotlin support
- **Google Mobile Services (GMS)** plugin for Firebase integration
- **Android SDK**: minSdk 23, targetSdk (latest)
- **Java Version**: 11
- **NDK Version**: 27.0.12077973

### **iOS Development**
- Native Swift integration
- Cocoapods for dependency management
- Xcode project configuration

### **Web Development**
- Flutter Web support
- HTML5 based rendering
- Service Workers and PWA capabilities

### **Desktop Support**
- Windows, macOS, and Linux through Flutter framework

---

## 🔐 Authentication Flow

```
User → Google Sign-In → Firebase Authentication → Firestore Database
                    ↓
              JWT Token Management
                    ↓
          Cloud Functions Authorization
```

---

## 💾 Data Management

### **Cloud Firestore Structure**
- Real-time synchronization across all client platforms
- Collections for:
  - User profiles (`user_model.dart`)
  - Social worker data (`social_worker_model.dart`)
  - Application-specific collections

### **Offline Support**
- Local Firestore caching
- Automatic sync when connection restored

---

## 🔄 Integration Points

### **Services Architecture**
Located in `lib/services/`:

1. **auth_service.dart** 
   - Firebase Authentication management
   - Google Sign-in integration
   - Session handling

2. **firestore_service.dart**
   - Cloud Firestore CRUD operations
   - Real-time data streaming
   - User & social worker data management

3. **ai_service.dart**
   - Likely calls to Google Cloud APIs or ML services
   - Backend AI operations via Cloud Functions

---

## 🌍 Firebase Project Configuration

**Project Name**: `urbaneye-002`

### **Configured Regions**
- ✅ Web
- ✅ Android
- ✅ iOS
- ✅ macOS
- ✅ Windows
- ❌ Linux (Firebase not configured)

### **Firebase Features Active**
- 🔑 Authentication
- 📊 Cloud Firestore
- ⚙️ Cloud Functions
- 📱 Google Sign-In
- 📊 Analytics (Measurement ID: G-BVEMZ2F1DB)

---

## 📊 Code Organization

```
lib/
├── main.dart                 # Application entry point
├── firebase_options.dart     # Firebase configuration
├── models/                   # Data models
│   ├── user_model.dart
│   └── social_worker_model.dart
├── services/                 # External service integration
│   ├── auth_service.dart            # Firebase Auth + Google Sign-In
│   ├── firestore_service.dart       # Cloud Firestore operations
│   ├── ai_service.dart              # AI/Backend APIs
│   └── (other services)
├── view_models/              # Business logic & state management
├── views/                    # UI screens
│   ├── auth/                 # Authentication screens
│   ├── civilian/             # Civilian user screens
│   └── social_worker/        # Social worker screens
├── widgets/                  # Reusable UI components
├── utils/                    # Helper utilities & constants
│   ├── app_colors.dart
│   ├── app_text_styles.dart
│   ├── constants.dart
│   └── validators.dart
└── firebase_options.dart     # Platform-specific Firebase config
```

---

## 🚀 Deployment & DevOps

### **Build Tools**
- **Flutter CLI** - Cross-platform build system
- **Gradle** - Android build automation
- **Xcode** - iOS build configuration
- **CMake** - Desktop platform builds

### **CI/CD Potential**
- GitHub Actions (repository ready for automation)
- Firebase Hosting for web deployment
- Google Play Console for Android
- Apple App Store for iOS

---

## 🔗 Google Cloud Ecosystem Usage

| Google Service | Purpose | Location |
|---|---|---|
| **Firebase Core** | Backend foundation | Across all services |
| **Firebase Auth** | User authentication | `auth_service.dart` |
| **Google Sign-In** | OAuth login | `auth_service.dart` |
| **Cloud Firestore** | Database & sync | `firestore_service.dart` |
| **Cloud Functions** | Serverless backend | Called via `ai_service.dart` |
| **Google Fonts** | Typography | `app_text_styles.dart` |
| **Google Analytics** | App analytics | Firebase configuration |
| **Google Mobile Services** | Android integration | `build.gradle.kts` |

---

## 📈 Scalability & Performance

- **Cloud Firestore**: Auto-scaling, serverless database
- **Cloud Functions**: Automatic scaling for backend operations
- **Firebase CDN**: Global content delivery for web
- **Offline-first**: Local caching with automatic sync

---

## 🛡️ Security Features

- ✅ Firebase Authentication with Google OAuth
- ✅ Firestore security rules (backend configured)
- ✅ Cloud Functions authorization
- ✅ API key management (platform-specific)
- ✅ JWT token-based session management

---

## 📝 Summary

**UrbanEye** leverages a **100% Google Cloud-native technology stack** for its backend infrastructure. From Firebase Authentication for user management to Cloud Firestore for real-time data synchronization and Cloud Functions for serverless backend logic, the application is built entirely on Google's ecosystem. Combined with Flutter for frontend development, this creates a modern, scalable, and maintainable application architecture.
