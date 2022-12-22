## Local & Session Storage vs @AppStorage & @SceneStorage

window.localStorage is an object that allows you to store data in key/value pairs in a web browser. It's part of the Web Storage API and is similar to sessionStorage, with the difference being that the data stored in localStorage persists even after the browser window or tab is closed, whereas data stored in sessionStorage is cleared when the browser window or tab is closed.

Keep in mind that localStorage and sessionStorage can only store strings, so you'll need to use JSON.stringify() to store objects and JSON.parse() to retrieve them.

Here's an example of how you can use localStorage to store and retrieve a value:

### JavaScript

```javascript

// Store a value in localStorage
localStorage.setItem('key', 'value');

// Retrieve a value from localStorage
let value = localStorage.getItem('key');
console.log(value); // Outputs 'value'


```

### SwiftUI

@AppStorage is a property wrapper in SwiftUI that allows you to store and retrieve values in the app's local storage. It's part of the AppStorage API and is similar to UserDefaults, with the difference being that @AppStorage is specific to SwiftUI and is more convenient to use in view code.

Here's an example of how you can use @AppStorage to store and retrieve a value:

```swift

struct ContentView: View {
    @AppStorage("key") var value: String = "default value"

    var body: some View {
        // The value can be used in the view code like any other property
        Text(value)
    }
}


```

You can also use @AppStorage to store and retrieve other types of values, such as integers, booleans, and even custom types that conform to the Codable protocol.
@AppStorage is a useful way to persist data across app launches and to store user preferences or application state in a way that is easy to use in view code. However, keep in mind that it is limited to storing small amounts of data and is not suitable for storing sensitive information or large amounts of data.

@SceneStorage is a property wrapper in SwiftUI that is used to store and retrieve the state of a view across different instances of the view. It is useful for preserving the state of a view when it is removed from the view hierarchy, such as when a view is moved to the background or when the app is suspended.

Here is an example of how to use @SceneStorage to store and retrieve the state of a view:
    
```swift

struct MyView: View {
    @SceneStorage("value") var storedValue: Int = 0

    var body: some View {
        VStack {
            Text("Stored value: \(storedValue)")
            Button("Increment value") {
                self.storedValue += 1
            }
        }
    }
}


```

In this example, @SceneStorage("value") declares a property wrapper that stores a value of type Int with the key "value". The stored value is initialized to 0 and can be modified using the storedValue property. When the view is removed from the view hierarchy, the value of storedValue is automatically saved and can be restored when the view is added back to the view hierarchy.

@SceneStorage is useful for preserving the state of views that are part of a multitasking interface, such as split view controllers and tab bar controllers, or for preserving the state of views that are part of a navigation interface.


[<< Return to index](README.md)