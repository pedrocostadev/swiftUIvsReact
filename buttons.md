## Buttons
In React, you can create a button using the button element. In SwiftUI, you can create a button using the Button view.
You can customize the button's appearance and behavior by using various properties and modifiers.


### React

```javascript

import React from 'react';

const SomeButton = () => (
    <button
        type="button"
        onClick={() => console.log('Button clicked')}
    >
        Click Me!
    </button>
)

```

### SwiftUI

```swift

import SwiftUI

struct SwiftUIView: View {
    var body: some View {
        Button {
            print("Button clicked")
        } label: {
            Label("Click Me!")
        }
    }
}

```


[<< Return to index](README.md)