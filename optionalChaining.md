## Optional Chainning


### JavaScript

```javascript

const book = {
    name: 'Hacking with Swift',
    author: {
        firstName: 'Paul',
        lastName: null
    }
}

// Won't break, will not print anything
console.log(book?.author?.lastName?.toUpperCase());

```

### SwiftUI

```swift

class Author {
  var firstName: String
  var lastName: String?
  
  init(first: String, last: String?) {
    firstName = first
    lastName = last
  }
}

class Book {
  var author: Author
  
  init(newAuthor: Author) {
    author = newAuthor
  }
}

var author = Author(first: "Paul", last: nil)

// Swift forces optional chaining , will print nil
print(author.lastName?.uppercased())


```