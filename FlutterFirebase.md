# Flutter and Firebase

1. add Firebase packages

```yaml
//for firebase
firebase_core: ^2.13.0 # If you need Firebase Core
firebase_auth: ^4.6.1 # If you need authentication
cloud_firestore: ^4.7.1 # If you need Firestore database
firebase_storage: ^11.2.1 # If you need Firebase Storage

// for firebase UI
firebase_ui_auth: ^1.4.1
```

2. configure Firebase Setting

Install FirebaseCLI + FlutterFireCLI
Run  ``` flutterfire configure ```  in console.

3. Initialize Firebase
```dart
void main() async {  
  // add this line  
  await Firebase.initializeApp(options: DefaultFirebaseOptions.currentPlatform,);   
  runApp(const MyApp());  
}
```

4. Firebase UI

Import login Provider
```dart
import 'package:firebase_ui_auth/src/providers/email_auth_provider.dart' as email_auth;
```
add login Providers to FirebaseUIAuth
```dart
void main() async {  
  await Firebase.initializeApp(options: DefaultFirebaseOptions.currentPlatform,); 
  // add this line -> here uses email 
  FirebaseUIAuth.configureProviders([email_auth.EmailAuthProvider()]);  
  runApp(const MyApp());  
}
```

ready to use 

```dart
SignInScreen(  
  actions: [AuthStateChangeAction<SignedIn>((context, state) {  
    print("signed in");  
  })],  
),
```
