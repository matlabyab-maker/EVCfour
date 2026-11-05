# EVCfour — Android Video Editor

Repository: `EVCfour`  
Application label: `EVCfour`  
Project version: `0.2.189` (`versionCode 389`)

## Project setup

- Android application module: `app`
- Gradle root project: `EVCfour`
- Application ID / namespace: `com.evc.app` (kept unchanged)
- Minimum Android SDK: 24
- Target / compile SDK: 35
- Java and Kotlin JVM target: 17
- Native ABI filter: `armeabi-v7a` only (32-bit ARM)
- Debug APK shrinking remains disabled.

## GitHub Actions

Workflow: `.github/workflows/android.yml`

- Runs on pushes to all branches (`branches: ["**"]`).
- Runs on pull requests targeting all branches.
- Supports manual execution with `workflow_dispatch`.

The workflow checks out the repository, configures JDK 17 and Android SDK 35, builds with Gradle 8.9, and uploads the ARM32 debug APK.

## Start a fresh repository

1. Create a new, empty GitHub repository named `EVCfour`.
2. Extract the contents of this ZIP and push the contents of the `EVCfour` folder to the repository root. Do not upload the parent folder as an extra nested directory.
3. In MGit, initialize this folder as a new Git repository, create the first commit, and set the remote to `https://github.com/matlabyab-maker/EVCfour.git` (if that is the account/repository owner).
4. Push to the branch you use. The workflow is configured for every branch.
5. In GitHub, confirm Actions are enabled and that `.github/workflows/android.yml` appears on the repository's default branch.

## Clean repository state

- Removed the embedded `.git` directory and all previous repository history/remotes.
- Preserved the Android source, resources, Gradle configuration, and workflow from the supplied EVCtree source archive.
- No nested duplicate project, build output, or Gradle cache is included.
- Application ID and Kotlin package names remain unchanged to avoid unnecessary app identity changes.

A successful build and on-device runtime behavior have not been verified in this environment. GitHub Actions must confirm the first build after the initial push.
