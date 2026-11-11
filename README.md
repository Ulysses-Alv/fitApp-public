> **Latest release: FitApp v0.22.1 (Build 48)** — [Download APK](https://github.com/Ulysses-Alv/fitApp-public/releases/download/v0.22.1/FitApp-v0.22.1.apk) · [Release notes](https://github.com/Ulysses-Alv/fitApp-public/releases/tag/v0.22.1)
>
> Install on Android 8.0 (API 26) or later. If prompted, allow your browser or file manager to install unknown apps.
# FitApp

**FitApp** is a local-first Android application for tracking and analyzing strength and hypertrophy training.

It started as a personal tool: I wanted a fast, offline-first workout tracker that matched the way I actually train instead of adapting my workflow to a generic fitness app. Over time, it evolved into a larger engineering project focused on progressive overload, training analytics, exercise selection, personal records, and long-term performance trends.

> This repository is the **public showcase and release channel** for FitApp.  
> The main application source code is kept private.

## What it does

- **Offline-first workout tracking** — log sets, repetitions, weight and RIR without requiring an internet connection.
- **1,300+ exercise catalog** with locally bundled exercise data and animations.
- **Progressive overload analytics** with estimated 1RM, historical comparisons and trend analysis.
- **Personal Record detection** across multiple PR categories, including weight, repetitions at a given load, estimated 1RM and set volume.
- **Training volume analysis** with effective-set and muscle-group tracking.
- **Period comparisons** to evaluate whether performance is improving, stable or declining across training blocks.
- **Routine generation and exercise replacement** using training context, exercise characteristics and user constraints.
- **Body measurement tracking** and historical comparison.
- **Optional cloud synchronization** while keeping the application usable offline.
- **In-app update flow** backed by GitHub Releases.

## Engineering highlights

FitApp is not just a collection of screens around a workout database. A large part of the project is a domain layer dedicated to training analysis.

Examples include:

- Policy-based **e1RM estimation** with an Epley implementation.
- **Primary editor for the dedicated engines for:
-  - exercise performance analysis,
-  - personal record detection,
  - volume analysis,
  - period comparison,
  - exercise transitions,
  - progression evidence,
  - training verdict synthesis.
- **Separation between **domain models, policies, estimators, repositories and UI**.
- Local-first repositories with optional Firebase-backed synchronization.
- **Exercise metadata represented through compact muscle-role bitmasks used by filtering, routine generation and recommendation logic.
- **Automated unit and integration coverage for the core analytics and training-domain logic.

The private codebase currently contains **40+ automated tests** covering areas such as progression analytics, e1RM estimation, PR detection, routine generation, measurements, synchronization and workout history.

## Tech stack

- **Kotlin**
- **Android / Jetpack Compose**
- **Gradle**
- **Local-first persistence**
- **Firebase Authentication / Firestore** for optional sync
- **GitHub Releases** for distribution and in-app updates

## Download

The latest APK is available from the repository's [Releases](https://github.com/Ulysses-Alv/fitApp-public/releases) section.

### Installation

1. Download the latest APK from Releases.
2. Allow installation from unknown sources if Android requests it.
3. Open the APK and complete the installation.

## Development approach

FitApp has also been an experiment in **AI-assisted software development**.

AI tools are used heavily during implementation, but the project is driven by explicit product requirements, domain rules, architecture decisions, iterative testing and manual validation. I define the behavior and constraints, review the generated implementation, reproduce failures, refine the design and maintain the application as a real tool that I use in my own training.

The goal of the experiment is not to measure how much code an AI can generate in one prompt, but how effectively AI can be incorporated into a disciplined software-engineering workflow.

## Project status

FitApp is primarily built for my own training workflow and is not currently intended to be a commercial fitness product.

That makes it a useful environment for experimenting with:

- training analytics,
- Android architecture,
- offline-first product design,
- domain modeling,
- automated testing,
- AI-assisted development workflows.

If the app happens to fit your training style too, feel free to use the APK from Releases.

---

Built and maintained by **Ulises Alvarenga**.
