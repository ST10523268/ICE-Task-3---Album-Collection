# ICE Task 3 - Album Collection App 

## 1. Introduction
The Album Collection application is a React Native mobile application built using TypeScript and Expo. It provides users with an interface to manage and view a personal collection of music albums, allowing for form submissions, data validation, adding multiple entries, and deleting albums.

## 2. Development Environment
The application was developed, debugged, and tested within the following environment:
* Expo: Framework used for building and running the React Native application.
* React Native: Cross-platform mobile framework utilized for UI components.
* TypeScript: Typed superset of JavaScript used to ensure strong type safety.
* Institutional VM: The virtualized workstation environment used for development.
* BlueStacks 5: The Android emulator environment initially intended for hosting and running the mobile app.
* Expo Go: The mobile client used to load and preview the application.

## 3. Error Log
The following table documents the errors identified and corrected within `App.tsx`:

| # | Location | Problem | Error Type | Correction |
|---|---|---|---|---|
| 1 | `App.tsx` | Missing `@react-native-picker/picker` package dependency in configuration. | Imports / Dependencies | **What was wrong:** The package was missing from project dependencies, causing an "Unable to resolve module" runtime error.<br>**Why it was wrong:** React Native Picker requires explicit installation in `package.json` to render dropdown components.<br>**What I changed:** Added `@react-native-picker/picker` to dependencies. |
| 2 | `App.tsx` | Form validation logic allowed short or empty text inputs to be submitted. | Logic / Validation | **What was wrong:** Input fields lacked sufficient minimum length enforcement and blank checks.<br>**Why it was wrong:** Users could accidentally submit invalid or incomplete album data into the state collection.<br>**What I changed:** Implemented strict validation checks for title, artist, and minimum length constraints. |
| 3 | `App.tsx` | Rating and year values permitted out-of-range numbers. | Runtime / Logic | **What was wrong:** Numerical inputs for year and rating could accept values outside acceptable bounds.<br>**Why it was wrong:** Could break data consistency or display unexpected UI behavior.<br>**What I changed:** Added boundary validation rules for numerical ranges. |

## 4. Testing
The corrected application was tested under the following core scenarios:
* Invalid Form Submission: Tested submitting forms with blank fields, missing artists, or invalid ratings to verify that error alerts and validation blocks function correctly.
* Valid Form Submission: Tested entering properly formatted album details to ensure the new record is successfully added to the list.
* Adding Multiple Albums: Tested adding several sequential albums to verify that the FlatList state updates correctly and handles multiple items without performance degradation.
* Deleting an Album: Tested the removal function to ensure specific album cards can be successfully deleted from the collection view.

## 5. Screenshots
<img width="382" height="811" alt="image" src="https://github.com/user-attachments/assets/d2fc12f2-adec-45be-97db-a75cd35010ac" />

<img width="374" height="824" alt="image" src="https://github.com/user-attachments/assets/ebef6362-2578-4159-8a97-e01ebd015526" />


*Note: The BlueStacks App Player and Expo Go experienced persistent loading and resolution issues during testing. As a result, Expo Snack was utilized to successfully verify, run, and capture the completed interface performance.*

## 6. Conclusion
Through investigating and correcting the Album Collection application, I gained a much deeper practical understanding of how to identify and resolve issues related to missing package dependencies, form validation logic, TypeScript types, and state management in React Native. Successfully debugging these components allowed me to build a stable, fully functional mobile interface that meets all structural and operational requirements.
