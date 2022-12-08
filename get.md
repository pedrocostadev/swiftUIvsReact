## HTTP Get Request


### JavaScript

```javascript

import React, { useEffect, useState } from 'react';

const Songs = () => {

    const [songs, setSongs] = useState([])

    useEffect(() => {
        const getSongs = async () => {
            const url = "https://itunes.apple.com/search?term=taylor+swift&entity=song")
            const songs = await fecth(url)
            const parsedSongs = await response.json();
            setSongs(parsedSongs)
        }
        getSongs();
    }, [])
    
    return (
        <ul>
            {songs.map(song => <li key={song.trackId}>{song.trackName}</li>)}
        </ul>
    )
}

```

### SwiftUI

```swift

import SwiftUI

struct Response: Codable {
    var results: [Result]
}

struct Song: Codable {
    var trackId: Int
    var trackName: String
}

struct ContentView: View {
    @State private var songs = [Song]()

    var body: some View {
        List(results, id: \.trackId) { song in
            VStack {
                Text(song.trackName)
            }
        }
        .task {
            await loadData()
        }
    }

    func loadData() async {
        guard let url = URL(string: "https://itunes.apple.com/search?term=taylor+swift&entity=song") else {
            print("Invalid URL")
            return
        }

        do {
            let (data, _) = try await URLSession.shared.data(from: url)
            if let decodedResponse = try? JSONDecoder().decode(Response.self, from: data) {
                results = decodedResponse.results
            }
        } catch {
            print("Invalid data")
        }

    }
}

```