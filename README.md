# auth-implemented
## Adding additional profile information

Two additional informations can be added to the user information as follows:
#### 1. Display Name
To add full name or any name for the purpose of displaying in the application.
#### 2. Photo URL
To add the url of the photo that can be used as profile picture.

### Below is the javascript code to add additional information.

```
// Fetching the current user
const user = firebase.auth().currentUser;

// Fetching value from a html input fields with id
const displayName = document.getElementById("name").value;
const photoURL = document.getElementById("photo").value;

// Updating additional information
user.updateProfile({
  displayName,
  photoURL
})
```

> To add additional data on `Sign Up`
```
function signUp() {

  // Fetching value from a html input fields with id
  const email = document.getElementById("email").value;
  const password = document.getElementById("password").value;
  
  // Fetching additional informations
  const displayName = document.getElementById("displayName").value;
  const photoURL = document.getElementById("photo").value;
  
  // Performing Sign Up Operation
  firebase.auth().createUserWithEmailAndPassword(email, password)
    .then((userCredential) => {
      // Updating additional information
      const user = userCredential.user;
      user.updateProfile({
        displayName,
        photoURL
      });
    })
};
