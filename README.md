# 🏋️ [GymApp]

[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.21-blue.svg?style=flat&logo=kotlin)](https://kotlinlang.org)
[![KMP](https://img.shields.io/badge/Kotlin-Multiplatform-blue.svg?style=flat&logo=kotlin)](https://kotlinlang.org/docs/multiplatform.html)
[![Compose](https://img.shields.io/badge/Compose-1.9.1-blue.svg?style=flat&logo=jetpackcompose)](https://www.jetbrains.com/compose-multiplatform/)

> Your intelligent fitness companion that transforms gym sessions into measurable progress

## 📱 What is it all about?

[GymApp] is a modern, cross-platform mobile application designed for gym enthusiasts who want complete control over their training journey. Built with Kotlin Multiplatform, it delivers a native experience on both Android and iOS while maintaining a single, robust codebase.

### 🎯 Core Features

- **Comprehensive Workout Logging** - Track exercises, sets, reps, and weights with precision
- **Intelligent Progress Analysis** - Automated analysis of your workout history to identify strengths and areas for improvement
- **Personalized Recommendations** - AI-driven DOs and DON'Ts based on your unique training patterns
- **Calorie Tracking** - Automatic calculation of calories burned during workouts
- **Body Measurements** - Monitor physical changes with height, weight, and custom measurements
- **Photo Progress** - Visual transformation tracking with before/after comparisons
- **Interactive Charts** - Detailed insights and visualizations to keep you motivated

## 🏗️ Architecture

[GymApp] is built with enterprise-grade architecture patterns, ensuring scalability, maintainability, and testability.

### Clean Architecture Layers

```
┌─────────────────────────────────────────┐
│         Presentation Layer              │
│  (States, UI States, Reducers, Events)  │
└─────────────────┬───────────────────────┘
                  │
┌─────────────────▼───────────────────────┐
│           Domain Layer                  │
│   (UseCases, Interactors, Mappers)      │
└─────────────────┬───────────────────────┘
                  │
┌─────────────────▼───────────────────────┐
│            Data Layer                   │
│  (Repositories, DataSources, Mappers)   │
└─────────────────────────────────────────┘
```

### MVI Pattern

The app implements Model-View-Intent architecture for predictable state management:

- **Model** - Immutable state representing the UI
- **View** - Composable functions that render the state
- **Intent** - User actions that trigger state changes
- **Reducer** - Pure functions that produce new states
- **Actor** - Side-effect handlers for async operations
- **Command** - One-time events (navigation, showing toasts)

### Multi-Modular Structure

Each common module is divided into:
- **`:something:api`** - Public contracts and interfaces
- **`:something:impl`** - Internal implementations (marked as `internal`)

Each UI feature is divided into:
- **`:di`** - dependency injection that builds a feature
- **`:domain_data`**:
- - **`:api`** - public contracts and interfaces
- - **`:impl`** - internal implementations (marked as `internal`)
- **`:navigation`** - public contracts and interfaces
- **`:presentation`**:
- - **`:api`** - public contracts and interfaces
- - **`:impl`** - internal implementations (marked as `internal`)


This approach ensures:
- Clear separation of concerns
- Reduced compile times
- Better encapsulation
- Easier team collaboration

## 🛠️ Tech Stack

### Core Technologies
- **Kotlin 2.2.21** - Modern, concise, and safe programming language
- **Kotlin Multiplatform** - Share business logic across Android and iOS
- **Compose Multiplatform 1.9.1** - Declarative UI framework

### Architecture & Patterns
- **Clean Architecture** - Separation of concerns across layers
- **MVI Pattern** - Unidirectional data flow
- **Dependency Injection** - Koin 4.1.1 for modular DI
- **Design Patterns** - Command, Builder, Factory, Mediator, Observer

### Networking & Serialization
- **Ktor 3.3.1** - Multiplatform HTTP client
- **Kotlinx Serialization 1.9.0** - Type-safe JSON parsing

### Database & Storage
- **Room 2.8.3** - Type-safe database abstraction
- **SQLite 2.6.1** - Local data persistence
- **DataStore 1.1.7** - Key-value storage for preferences

### UI & Image Loading
- **Jetpack Compose** - Modern declarative UI
- **Coil 3.3.0** - Efficient image loading
- **Navigation Compose 2.9.1** - Type-safe navigation

### Utilities
- **Kotlinx DateTime 0.7.1** - Cross-platform date/time handling
- **Kotlinx Coroutines 1.10.2** - Asynchronous programming
- **Napier 2.7.1** - Multiplatform logging
- **Immutable Collections 0.4.0** - Thread-safe collections

## 🎨 Design Principles

We follow industry best practices:

- **KISS** (Keep It Simple, Stupid) - Simplicity over complexity
- **DRY** (Don't Repeat Yourself) - Single source of truth
- **YAGNI** (You Aren't Gonna Need It) - Build what's needed now
- **SOLID** - Object-oriented design principles
- **Separation of Concerns** - Each module has a single responsibility

## 📂 Project Structure

```
TBD
```

## 🚀 Getting Started

### Prerequisites

- Android Studio Ladybug | 2024.2.1 or later
- Xcode 15.0+ (for iOS development)
- JDK 17 or later
- Kotlin 2.2.21


## 🧪 Testing Strategy

- **Unit Tests** - Business logic validation (JUnit, Kotlin Test)
- **Integration Tests** - Repository and UseCase testing
- **UI Tests** - Compose UI testing with Espresso
- **Koin Tests** - DI configuration validation

## 📄 License

TBD

## 👨‍💻 Author

**Your Name**
- GitHub: [@khyzhun](https://github.com/khyzhun)
- LinkedIn: [Alexander Khyzhun](https://linkedin.com/in/khyzhun)

## 🙏 Acknowledgments

- I wanna thank me (c) Snoop
