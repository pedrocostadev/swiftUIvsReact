## Lists
In React.js, a list can be created using the map function to iterate over an array of items and return a list of elements.
In SwiftUI, a list can be created using the List view. The List view takes an array of items and displays them in a vertically scrolling list. Each item in the list can be created using a Row view or any other custom view that you define.

### React

```javascript

import React from 'react';

function List(props) {
  const items = ['item 1', 'item 2', 'item 3'];
  return (
    <ul>
      {items.map(item => (
        <li key={item}>{item}</li>
      ))}
    </ul>
  );
}

```

### SwiftUI

```swift

import SwiftUI

struct ContentView: View {
  let items = ["item 1", "item 2", "item 3"]
  
  var body: some View {
    List(items, id: \.self) { item in
      Text(item)
    }
  }
}

```


[<< Return to index](README.md)