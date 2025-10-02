workflows:
  build-android:
    name: Build Android APK
    max_build_duration: 60
    environment:
      flutter: stable
      xcode: latest
      vars:
        PACKAGE_NAME: "com.example.timeorganizer"
    scripts:
      - name: Install dependencies
        script: |
          flutter pub get
      - name: Build APK (release)
        script: |
          flutter build apk --release
    artifacts:
      - build/app/outputs/flutter-apk/app-release.apk
