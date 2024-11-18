# MyHelper
  MyHelper is a multi-functional Flutter application designed to provide users with various utility tools, such as 
  authentication, battery monitoring, network status, device information, location tracking, contact management, 
  messaging, and photo handling. It features Firebase integration for backend services and a modern dark mode toggle.

##Table of Contents
   1) Features
   2) Tech Stack
   3) Database Specification
   3) Installation
   4) Folder Structure
   5) Usage
   6) Contributing
   7) License

## Features
   1.User Authentication
      -Login and Signup pages using Firebase Authentication.
   2.Dashboard
      -Centralized access to app features.
      -Includes a toggle for dark and light modes.
   3.Utility Tools
      -Battery Monitoring: Displays battery status.
      -Device Information: View device specifications.
      -Network Monitoring: Check current network status.
   4.Communication Tools
      -Contact Management: Manage user contacts.
      -Messaging: View and interact with message lists.
   5.Media Tools
      -Photo Management: Access and manage photos.
   6.Location Services
     -Track and manage user location.
   7.Dynamic Themes
     -Easily switch between light and dark modes.
     
##Tech Stack
   1.Frontend: Flutter (Dart)
   2.Backend: Firebase
     Authentication
     Cloud Storage
     Firestore
   3.State Management: Stateful Widgets
   4.Routing: go_router package for declarative navigation.
  
## *Database Specification*

    The project "MyHelper(Phone Access from Anywhere)" uses *Firebase Firestore* as its primary database. Below is the detailed specification:  

###  *1. Database Type*  
       - *Type*: NoSQL Cloud Database  
       - *Service*: Firebase Firestore  
       - *Data Structure*: Document-based with collections and documents.  

###  *2. Data Models and Structure*  
       -The data is organized into collections, each containing documents. Key collections and their fields include:  

       - *Users*:  
          - uid (String): Unique identifier for each user.  
          - fullName (String): User's full name.  
          - email (String): User's email address.  
          - profilepic (String): URL to the profile picture stored in Firebase Storage.  
        
       - *Contacts*:  
          - displayname (String): Contact's name.  
          - phonenumber (String): Contact's phone number.  

       - *Messages*:  
         - threadId (String): Unique ID for the message.   
         - address (String): Recipient’s phone number.  
         - body (String): Content of the message.  
         - date (DateTime):Date and Time when the message was sent.
         - isread :to be saved true, if message is read.   
 
      - *DeviceInfo*: Information about device(e.g., manufacturer, model , android version , android SDK,security patch etc).    
      - *batteryInfo* : Information about the battery (e.g., level, health, temperature etc).  
      - *networkInfo* : Information about the network (e.g., wifi_name,wifi_BSSID etc).  

### *3. Security Rules*  
       Firebase Firestore uses strict security rules to protect user data:  
        - Only authenticated users can access their own data.  
        - Role-based access controls are applied to restrict access to sensitive data.  

### *4. Data Synchronization*  
       Firestore provides real-time updates, ensuring that data remains in sync across all connected devices.  

### *5. Backup and Scalability*  
       - Firebase automatically backs up data and offers horizontal scaling, allowing the database to handle a growing user base seamlessly.  

       This database specification ensures the system is robust, secure, and scalable for user needs. 

## Installation 
    -Prerequisites
       1.Flutter SDK
       2.Firebase project configured with proper API keys.  
    -Steps:
     1.Clone the repository:
        git clone https://github.com/Kalashsatyapal/MyHelper.git
     2.Navigate to the project directory:
        cd MyHelper
     3.Install dependencies:
        flutter pub get
     4.Configure Firebase:
       Replace Firebase configuration details in main.dart with your project details:  
         FirebaseOptions(
            apiKey: 'YOUR_API_KEY',
            appId: 'YOUR_APP_ID',
            messagingSenderId: 'YOUR_SENDER_ID',
            projectId: 'YOUR_PROJECT_ID',
            storageBucket: "YOUR_STORAGE_BUCKET",
            );
     5.Run the app:
         flutter run
         
##Folder Structure
        lib/
        ├── core/
        │   └── theme/
        │       └── app_theme.dart      # Theme management
        ├── features/
        │   ├── auth/
        │   │   └── presentation/
        │   │       ├── login_page.dart
        │   │       ├── signup_page.dart
        │   │       └── splash_screen.dart
        │   ├── dashboard/
        │   │   └── presentation/
        │   │       └── dashboard_page.dart
        │   ├── contact/
        │   │   └── presentation/
        │   │       └── contact_page.dart
        │   ├── location/ 
        │   │   └── presentation/
        │   │       └── location_page.dart
        │   ├── message/
        │   │   └── presentation/
        │   │       └── messagelist.dart
        │   ├── photo/
        │   │   └── photopage.dart
        │   ├── Battery/
        │   │   └── Battery_page.dart
        │   ├── Device/
        │   │   └── Device.dart
        │   └── Network_page/
        │       └── Network_page.dart

##Usage
  -Navigation
    The app uses go_router for managing routes. Each feature is mapped to a specific route:
    
   Feature	             Route
   Splash Screen	         /
   Login Page	             /login
   Signup Page	           /signup
   Dashboard	             /dashboard
   Contact Management	     /contacts
   Messaging	             /conversationlistscreen
   Location Tracking	     /location
   Photo Management	       /photo
   Battery Monitoring	     /Battery
   Device Information	     /Device
   Network Monitoring	     /Network

##Contributing
  -Contributions are welcome! Here's how you can contribute:
   1.Fork the repository.
   2.Create a new branch:
     git checkout -b feature-branch-name
   3.Make your changes and commit:
     git commit -m "Add your message"
   4.Push to the branch:
     git push origin feature-branch-name
   5.Open a pull request.  

##License
   This project is licensed under the MIT License. See the LICENSE file for details.
