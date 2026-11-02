# login_page

A visual-only Flutter login and registration screen from February 2021, written by [Mathis Bois](https://github.com/corbo-fr) as an early Flutter exercise. The connection and register screens use the same visual shell. Pressing a button pushes a route, and the field values are never submitted.

## Screens

Both screens use a blue gradient (`Colors.blue[200]`, `Colors.blue[700]`, `Colors.blue[900]`), a Flutter logo loaded from the network, and the title **Flutter Login** in the Exo family via `google_fonts`. The debug banner is hidden.

### Connection

[`LoginPage`](lib/main.dart) is the home route. The subtitle is `connection`.

- A login field (person icon) and a password field (lock icon, obscured).
- A white **CONNECTION** button.
- **register** and **recovery** text buttons.

**CONNECTION**, **register**, and **recovery** each push the register screen. The fields have no controllers, so the typed values are never read.

### Register

[`SignupPage`](lib/signup-page.dart). The subtitle is `register`.

- Login, email, and password fields (person, mail, and lock icons). The password is obscured.
- A white **REGISTER** button.
- A **connection** text button.

**REGISTER** and **connection** each push another copy of this same screen. The system back action is what returns to the previous route. There is no separate recovery screen: **recovery** on the connection screen opens this one.

## Stack

- **Flutter** 1.22.6 stable, framework revision [`9b2d32b`](https://github.com/flutter/flutter/commit/9b2d32b605630f28625709ebd9d78ab3016b2bf6) (25 January 2021), recorded in [`.metadata`](.metadata). That release ships **Dart 2.10.5**.
- **Dart constraint** in [`pubspec.yaml`](pubspec.yaml): `>=2.7.0 <3.0.0`. [`pubspec.lock`](pubspec.lock) was resolved for Dart 2.10.x and Flutter below 2.0. The sources are pre-null-safety.
- **App** package name `login_page`, version `1.0.0+1`. Android application id and iOS bundle id are `com.example.login_page`. The on-device label is `login_page`.
- **UI** Material. The buttons are `RaisedButton` and `FlatButton`, the button widgets shipped with Flutter 1.22.
- **Font** direct dependency [`google_fonts`](https://pub.dev/packages/google_fonts) 1.1.2. `GoogleFonts.exo` downloads Exo when the screen builds. No font files are bundled in the repo.
- **Android** minSdk 16, compile and target SDK 29, Kotlin 1.3.50, Android Gradle Plugin 3.5.0, Gradle 5.6.2. The runner uses the v2 embedding.
- **iOS** deployment target 9.0, standard Flutter `Runner`.

Also declared in `pubspec.yaml`, and not imported by either screen: `cupertino_icons` 1.0.0, `english_words` 3.1.5, and `animate_do` 1.7.5.

`images/hotel_1.jpeg` and `images/hotel_2.jpeg` are listed under `flutter: assets` and are not referenced. `images/cat.jpeg` and `images/catgif.gif` are in the tree and are not assets. They remain from the February 2021 scaffold. The Android Kotlin file still lives under `android/app/src/main/kotlin/com/example/choupi/`, and the Visual Studio Code launch config is still named `choupi`.

The repository has Android and iOS runners only. There is no test suite.

## Run

Use Flutter 1.22.6. `RaisedButton` and `FlatButton` were removed in Flutter 3.3, and the Dart SDK constraint stops below 3.0, so a current stable Flutter SDK will not resolve or compile this project unchanged.

It was developed in Visual Studio Code with the Flutter and Dart extensions ([`.vscode/launch.json`](.vscode/launch.json)). The toolchain recorded with the February 2021 screenshots was Xcode 12.4, Android Studio 4.2 preview, and Java 8 update 281.

```bash
flutter --version   # Flutter 1.22.6 · Dart 2.10.5
flutter pub get
flutter devices
flutter run
```

The logo is an `Image.network` request to a Medium CDN URL, and Exo is fetched by `google_fonts`. The emulator or device needs a network connection for the logo and the title font to appear.

## Screenshots

Device frames captured in February 2021 and stored in [`.demo/`](.demo/).

### iPhone 12 Pro Max

| Connection | Register |
| --- | --- |
| ![Connection screen on an iPhone 12 Pro Max: blue gradient, Flutter logo, login and password fields, CONNECTION button, register and recovery links](.demo/iphone_12_pro_max_screen_1.png) | ![Register screen on an iPhone 12 Pro Max: blue gradient, Flutter logo, login, email, and password fields, REGISTER button, connection link](.demo/iphone_12_pro_max_screen_2.png) |

### Pixel 3a XL

| Connection | Register |
| --- | --- |
| ![Connection screen on a Pixel 3a XL](.demo/pixel_3a_xl_screen_1.png) | ![Register screen on a Pixel 3a XL](.demo/pixel_3a_xl_screen_2.png) |
