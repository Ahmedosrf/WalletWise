# WalletWise — Offline-First Personal Finance for Arabic Users

[![Flutter](https://img.shields.io/badge/Flutter-3.x-02569B?logo=flutter&logoColor=white)](https://flutter.dev/)
[![Dart](https://img.shields.io/badge/Dart-3.x-0175C2?logo=dart&logoColor=white)](https://dart.dev/)
[![License](https://img.shields.io/badge/license-MIT-2ea44f?logo=opensourceinitiative&logoColor=white)](LICENSE)
[![Language](https://img.shields.io/badge/UI-Arabic%20%7C%20RTL-0F766E)](#)

> **WalletWise** is an Arabic-first, offline-first mobile finance application for recording expenses, managing budgets, and understanding household spending in low-connectivity environments.

## Product Overview

WalletWise is designed around a practical constraint: financial tools should remain useful even when connectivity is unreliable. The application combines fast local expense capture with optional cloud-backed services for authentication, synchronization, and AI-assisted extraction. Its interface is built for Arabic-speaking users and supports right-to-left presentation.

The project was developed for **SalamHack 2026** by a Palestine-based team.

## Core Capabilities

| Capability | What it provides |
|---|---|
| **Expense capture** | Manual entry, receipt-based entry, voice-based entry, and SMS-oriented workflows. |
| **Budgeting** | Category budgets, spending summaries, notifications, and progress tracking. |
| **Reports** | Visual summaries, monthly comparisons, and category-level spending analysis. |
| **AI assistance** | Gemini-powered workflows for extracting information from receipts and voice input. |
| **Family finance** | Shared household workflows with role-oriented access patterns. |
| **Offline-first storage** | Local persistence through `SharedPreferences`, so core interactions do not depend on a live connection. |
| **Arabic UX** | RTL-ready screens and terminology designed for Arabic users. |

## Technical Architecture

The application is implemented as a Flutter client with a separation between presentation, domain models, and service integrations.

| Layer | Implementation |
|---|---|
| Mobile UI | Flutter and Dart |
| Local persistence | `SharedPreferences` through `LocalService` |
| Authentication and cloud data | Firebase Authentication and Cloud Firestore |
| Additional backend integration | Supabase client integration |
| Media input | `image_picker` for receipt and image workflows |
| Network integrations | `http` package and service-layer wrappers |
| Visual design | Custom Flutter widgets, RTL layouts, and application theme constants |

## Repository Structure

```text
lib/
├── constants/       # Theme and shared UI constants
├── models/          # Domain models such as transactions
├── screens/         # Feature-oriented Flutter screens
└── services/        # Firebase, Supabase, and local persistence services
assets/              # Application assets and logo
android/             # Android platform project
pubspec.yaml         # Flutter dependencies and configuration
LICENSE              # MIT license
```

## Local Development

### Prerequisites

Install the Flutter SDK compatible with the Dart constraint in [`pubspec.yaml`](pubspec.yaml), then verify the environment:

```bash
flutter doctor
```

### Installation

```bash
git clone https://github.com/Ahmedosrf/WalletWise.git
cd WalletWise
flutter pub get
```

### Run the application

```bash
flutter run
```

To target a specific device, use `flutter devices` followed by `flutter run -d <device-id>`.

## Configuration and Security

Some services require platform configuration and valid credentials. Configure Firebase and Supabase through the normal Flutter platform setup before enabling cloud-backed features. Do not commit API keys, service-account files, or production credentials. Use local or CI secrets for environment-specific configuration and review the repository history if a credential is ever exposed.

The application is intended to keep core local interactions available offline; cloud synchronization and remote AI features naturally require connectivity.

## Demonstration

[![WalletWise Demo](https://img.youtube.com/vi/y7aqvFgPtDo/0.jpg)](https://youtube.com/shorts/y7aqvFgPtDo)

## Team

| Contributor | Role |
|---|---|
| Ahmed Wasam Alhayek | Project Lead / Pitcher |
| Ahmed Mamoun Osrof | Mobile Developer |
| Eid Ahmed Abu Beid | UI/UX Designer |

**Location:** Palestine, Gaza.

## Roadmap

Potential next steps include adding automated Flutter tests, introducing a formal environment configuration layer, improving synchronization conflict handling, and documenting the AI extraction contracts with representative test fixtures.

## License

WalletWise is distributed under the [MIT License](LICENSE).

## Contact

Maintained by [Ahmed Osrof](https://github.com/Ahmedosrf). For project-specific questions, please open a GitHub issue with a reproducible description and the affected platform.
