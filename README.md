# Flutter Build and Publish APK

A composite GitHub Action that builds a Flutter Android APK and uploads it as a workflow artifact.

## Usage

```yaml
- uses: actions/checkout@v4
- uses: Dank-del/flutter-build-and-publish-action@v2
```

## Inputs

| Name | Description | Required | Default |
| --- | --- | --- | --- |
| `flutter-version` | Flutter version, e.g. `3.24.3`. Empty means latest on the chosen channel. | no | `''` |
| `flutter-channel` | `stable`, `beta`, or `master`. | no | `stable` |
| `java-version` | Java version installed via Temurin. | no | `17` |
| `build-args` | Arguments passed to `flutter build`. | no | `apk --split-per-abi` |
| `artifact-name` | Name for the uploaded artifact. | no | `flutter-apk` |
| `working-directory` | Path to the Flutter project root. | no | `.` |

## Outputs

| Name | Description |
| --- | --- |
| `apk-path` | Directory containing the built APKs. |

## Example

```yaml
name: Build APK

on:
  push:
    branches: [main]
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - uses: Dank-del/flutter-build-and-publish-action@v2
        with:
          flutter-channel: stable
          flutter-version: 3.24.3
          build-args: apk --release --split-per-abi
          artifact-name: my-app-apk
```

## Notes

The `v1` tag points to an earlier, broken version. Use `v2`.

## License

MIT
