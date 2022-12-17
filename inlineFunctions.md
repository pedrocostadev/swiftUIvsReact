## Inline functions

### React

```javascript

import React from 'react';

const Name = () => {
    return (
        <button
            type="button"
            onClick={() => console.log("This is a print inside an inline function")}
        >
            Click Me
        </button>
    )
}

```

### Swift

```swift

import SwiftUI

struct SwiftUIView: View {

    var body: some View {
        Button("Click Me") {
            print("This is a print inside an inline function")
        }
    }
}

```


[<< Return to index](README.md)