## Local State

### React

```javascript

import React, { useState } from 'react';

const Name = () => {
    
    const [name, setName] = useState('')

    return (
        <label>
            Name
            <input
                name="name"
                value={name}
                onChange={ev => setName(ev.target.value)}
            />
        </label>
    )
}

```

### Swift

```swift

import SwiftUI

struct SwiftUIView: View {

    @State private var name = ""

    var body: some View {
        TextField("Name", text: $name)
    }
}

```

@State should be used with simple struct types such as String, Int, and arrays, and generally shouldn’t be shared with other views. If you want to share values across views, you should probably use @StateObject ensuring that all views will be refreshed when the data changes.


[<< Return to index](README.md)