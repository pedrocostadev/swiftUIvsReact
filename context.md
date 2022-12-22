## Context vs @EnvironmentObject

React Context is a way to share values across a tree of React components without having to pass props down manually through every level of the tree. It provides a way to pass data through the component tree without having to pass props down manually at every level.
To use Context, you need to create a Context object using React.createContext. This creates an object with a Provider and a Consumer. The Provider is used to provide the data to its descendants, and the Consumer is used to access the data from the Provider.

### React

```javascript

import React from 'react';

// Create a Context object
const MyContext = React.createContext();

function App() {
  // Provide a value for the Context
  return (
    <MyContext.Provider value="Hello World">
      <MyComponent />
    </MyContext.Provider>
  );
}

function MyComponent() {
  // Access the value from the Context
  return (
    <MyContext.Consumer>
      {value => <div>{value}</div>}
    </MyContext.Consumer>
  );
}

```

### SwiftUI

In SwiftUI, @EnvironmentObject is a property wrapper that allows you to inject an object into the environment of a view hierarchy. This object can be accessed by any view in the hierarchy, and any changes to the object will be automatically reflected in all views that use it.

To use @EnvironmentObject, you first need to define a class or struct that represents the data you want to inject into the environment. This class or struct should conform to the ObservableObject protocol, which allows it to be observed by SwiftUI views.

Here's an example of a class that represents a user's login status, which conforms to ObservableObject:

```swift

class LoginStatus: ObservableObject {
  @Published var isLoggedIn = false
}

struct ContentView: View {
  @EnvironmentObject var loginStatus: LoginStatus

  var body: some View {
    if loginStatus.isLoggedIn {
      Text("Logged in")
    } else {
      Text("Not logged in")
    }
  }
}


```


[<< Return to index](README.md)