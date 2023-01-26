## Map loops


### JavaScript

```javascript

const someRandomUsers = [
    {firstName: 'Joe', lastName: 'Doe'},
    {firstName: 'Catarina', lastName: 'Machado'},
]

// Map
const usersFullNames = someRandomUsers.map(user => `${user.firstName} ${user.lastName}`)

```

### SwiftUI

```swift

struct User {
    let firstName: String
    let lastName: String

    init(firstName: String, lastName: String) {
        self.firstName = firstName
        self.lastName = lastName
    }
}

let someRandomUsers = [
    User(firstName: "Joe",lastName: "Doe"),
    User(firstName: "Catarina",lastName: "Machado"),
]

// Map
let usersFullNames = someRandomUsers.map { "\($0.firstName) \($0.lastName)" }


```


[<< Return to index](README.md)