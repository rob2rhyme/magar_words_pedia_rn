# magar_words_pedia_rn

A React Native + TypeScript app for crowdsourcing and browsing user-contributed definitions, explanations, and examples of words and concepts. Built with Expo, AWS Amplify (Cognito, AppSync + DataStore), secure storage, offline-first sync with conflict resolution, and a robust CI/CD pipeline.

---

## Features

- **Authentication**  
  - Email/password & social sign-in (Google, Apple) via AWS Cognito  
  - Secure token storage (SecureStore / Keychain / Keystore)

- **Crowdsourced Knowledge**  
  - Create, edit, and browse **Topics**  
  - Add **Contributions** (text, images, links) to each topic  
  - User profiles with avatars and contribution history

- **Offline-First Data Layer**  
  - AWS Amplify DataStore with local SQLite persistence  
  - Automatic sync when online  
  - Model versioning (`_version`) and custom conflict resolution

- **Conflict Minimization & Resolution**  
  - Optimistic concurrency with version numbers  
  - Lambda‐based AppSync resolvers for custom merge logic  
  - UI indicators for syncing state and conflict alerts

- **UI & UX**  
  - React Navigation (stack & tabs)  
  - Tailwind-style styling with `twrnc` (or React Native Paper)  
  - React Hook Form + Yup for contribution forms and validation  
  - Reusable components (e.g. `CrowdsourcedItemCard`)

- **Security & Best Practices**  
  - Enforce HTTPS (iOS ATS, Android Network Security Config)  
  - Fine-grained IAM / AppSync & Firestore security rules  
  - Dependency audit and runtime monitoring (CloudWatch / Firebase Analytics)

- **Testing & CI/CD**  
  - Unit tests with Jest & React Native Testing Library  
  - E2E tests with Detox (mobile) or Cypress (web)  
  - GitHub Actions for lint, type-check, tests, and builds  
  - Expo Application Services (EAS) / App Center for build & distribution

- **Beta Release**  
  - TestFlight (iOS) & Google Play internal track (Android)  
  - Feedback collection & bug triage

---

## Getting Started

### Prerequisites

- Node.js (>= 16)
- Yarn (>= 1.22) or npm
- Expo CLI  
  ```bash
  npm install -g expo-cli
## AWS Amplify CLI
npm install -g @aws-amplify/cli

##Installation
# 1. Clone repo
git clone https://github.com/rob2rhyme/magar_words_pedia_rn.git
cd magar_words_pedia_rn

# 2. Install dependencies
yarn install

# 3. Initialize Amplify backend
amplify init
amplify add auth      # configure Cognito
amplify add api       # configure AppSync GraphQL
amplify push          # deploy backend

# 4. Generate DataStore models
amplify codegen models

## Running the App
# Start Metro bundler
yarn start

# Run on iOS simulator
yarn ios

# Run on Android emulator
yarn android

##Project Structure
magar_words_pedia_rn/
├─ .github/                   # GitHub Actions workflows
├─ amplify/                   # Amplify project configuration
├─ src/
│  ├─ api/                    # AWS Amplify / AppSync wrappers
│  ├─ auth/                   # Auth context, hooks, screens
│  ├─ components/             # Reusable UI components
│  ├─ config/                 # aws-exports.js, environment configs
│  ├─ models/                 # Generated DataStore TypeScript models
│  ├─ navigation/             # React Navigation stacks & tabs
│  ├─ screens/                # Feature screens (Home, Topic, Profile)
│  ├─ store/                  # DataStore setup or Redux slices
│  ├─ theme/                  # Tailwind/React Native Paper themes
│  ├─ utils/                  # Helpers (formatters, validators)
│  └─ App.tsx                 # Entry point & navigation container
├─ .eslintrc.js               # ESLint configuration
├─ .prettierrc                # Prettier configuration
├─ tsconfig.json              # TypeScript settings (strict mode)
├─ package.json
└─ README.md

##
