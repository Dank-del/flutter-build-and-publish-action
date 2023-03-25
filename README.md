# Builds Workflow
This GitHub Actions workflow automatically builds and releases the Flutter app for Android on the master branch of the repository. The workflow runs on a macOS virtual machine provided by GitHub and uses the latest version of macOS available at the time of the build.

# Workflow Overview
## The workflow performs the following steps:

1. Set up JDK 11 for the build environment.
2. Clone the Flutter repository with the master channel.
3. Enable macOS desktop support for the Flutter project.
4. Check out the AniWatch code.
5. Get the required Flutter packages.
6. Build the app for Android, targeting the APK file format and splitting it into multiple files based on the target architecture.
7. Upload the built APK files as artifacts to the GitHub repository.
8. Create a GitHub release with the built APK files.

