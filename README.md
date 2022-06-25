# Clean Architecture Note App (MVVM / CRUD / Jetpack Compose)

Note app representing the usage of Clean Architecture in Android.

## Architecture Overview

The project is divided in three type of modules:

* The `app` module - contains app level and scaffolding classes that bind the rest of the codebase, 
such as MainActivity, NoteApp and app-level controlled navigation.
* `feature_` modules - feature specific modules which are scoped to handle a single responsibility 
in the app. These modules can be reused by any app, including test or other flavoured apps, when 
needed, while still keeping it separated and isolated. If a class is needed only by one feature 
module, it should remain within that module. If not, it should be extracted into an appropriate core 
module. A feature module should have no dependencies on other feature modules. They only depend on 
the core modules that they require.
* `core_` modules - common library modules containing auxiliary code and specific dependencies that 
need to be shared between other modules in the app. These modules can depend on other core modules, 
but they shouldn’t depend on feature nor app modules.

How Clean Architecture is structured:

Each feature contain three packages, `data`, `domain`, and `presentation`.

The `data` package contain the implementation of data sources, like a Room database or Retrofit API, 
and the implementation of the repositories.

The `domain` package contain business logic code including the definition of the models, the repositories 
interfaces and most important, the use cases.

The `presentation` package contain all the screens and ViewModels

## Learning Resources

* [Clean Architecture Tutorial for Android: Getting Started](https://www.raywenderlich.com/3595916-clean-architecture-tutorial-for-android-getting-started)
* [How to Make a Clean Architecture Cryptocurrency App (MVVM, Use Cases, Compose) - Android Studio](https://www.youtube.com/watch?v=EF33KmyprEQ)
* [How to Make a Clean Architecture Note App (MVVM / CRUD / Jetpack Compose) - Android Studio Tutorial](https://www.youtube.com/watch?v=8YPXv7xKh2w)