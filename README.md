# Smart Expense Tracker – Flutter Android Application

**Course / Programme:** Flutter Application Development Programme  
**Department:** Computer Science and Engineering (CSE)  
**Project Name:** Smart Expense Tracker  
**Target Platform:** Android (Compatible with Flutter Web)  

---

## 1. Project Overview

Smart Expense Tracker is a modern, responsive personal finance Android application developed in Flutter. It empowers users to record daily expenditures, categorize transactions, track monthly spending budgets, and visualize category distributions through interactive charts.

All data is stored locally on the device using **SharedPreferences**, ensuring complete privacy and offline persistence without requiring cloud servers.

---

## 2. Key Features

- **Financial Dashboard:** Total expenditure KPI, current month expenditure, category donut breakdown, and recent transactions.
- **Full Expense History:** Searchable expense list with category filters and interactive empty/loading/error states.
- **Validated Input Form:** Numeric constraint checking (> ₹0), category picker, and interactive date picker.
- **Detailed Transaction View:** Full details card with safety confirmation before permanent deletion.
- **Modern Material Design 3:** Dynamic Color Scheme seeded with emerald teal (`#006C50`) supporting both Light and Dark themes.

---

## 3. Technology Stack

- **Framework:** Flutter 3.35+
- **Language:** Dart 3 (Null Safety)
- **State Management:** Provider with ChangeNotifier
- **Persistence:** SharedPreferences (`shared_preferences`)
- **Charts:** fl_chart
- **Design System:** Material Design 3

---

## 4. How to Run the Project

### Prerequisites
1. Install [Flutter SDK](https://docs.flutter.dev/get-started/install) (3.35 or newer).
2. Install [Android Studio](https://developer.android.com/studio) with Android SDK and an Emulator or physical device.

### Step-by-Step Commands

```bash
# 1. Clone repository
git clone https://github.com/your-username/smart-expense-tracker.git
cd smart-expense-tracker

# 2. Install dependencies
flutter pub get

# 3. Run automated widget test
flutter test

# 4. Run application in debug mode on connected device
flutter run

# 5. Build production Release APK for college submission
flutter build apk --release
```

The generated APK will be available at:  
`build/app/outputs/flutter-apk/app-release.apk`

---

## 5. Team Contribution Matrix

| Team Member | Roll / Reg No | Key Modules Assigned |
| :--- | :--- | :--- |
| **Member 1 (Lead)** | CSE-01 | Architecture, Provider State Management, SharedPreferences Service |
| **Member 2** | CSE-02 | Dashboard Screen, fl_chart Category Visualization, App Theme |
| **Member 3** | CSE-03 | Add Expense Form with Validation, Date Picker, Input Formatters |
| **Member 4** | CSE-04 | Expense List Screen with Search/Filters, Detail Screen, Widget Tests |

---

## 6. Defect Log (Testing & Resolution)

| Defect ID | Description | Severity | Fix Applied | Status |
| :--- | :--- | :--- | :--- | :--- |
| **DEF-01** | Negative amount or zero could be saved | High | Added `double.tryParse(val) > 0` check in validator | Closed |
| **DEF-02** | Keyboard blocked form button on small screens | Medium | Wrapped form body in `SingleChildScrollView` | Closed |
| **DEF-03** | Date format looked messy in list view | Low | Formatted with `intl` package (`dd MMM yyyy`) | Closed |
| **DEF-04** | Chart threw divide-by-zero when expenses empty | High | Added empty fallback card when `totalSpent == 0` | Closed |
| **DEF-05** | App threw error on fresh install before any save | Medium | Handled null string safely in `StorageService.loadExpenses()` | Closed |
