# playlistix

playlistix for Spotify is a Single Page Application that you can use to export and import your Spotify playlists. There are already many apps out there to do this but most require separate user accoounts and/or involve backend services where you can't really transparently observe what happens with your user data. In contrast, playlistix...
- runs only in your browser. All required data is stored in your browser's local storage and the app does not communicate with anything except the [Spotify API](https://developer.spotify.com/documentation/web-api/).
- is really simple. It has an easy UI, and is built with a single HTML page powered by the minimalistic frameworks [Alpine.js](https://alpinejs.dev/) and [Pico.css](https://picocss.com/).
- is open source. You can view and modify the source code however you want.

To use playlistix, you have to log in to your Spotify account. You will need to grant the permissions `playlist-read-private` and `playlist-read-collaborative`. The app uses the [Authorization Code Flow with Proof Key for Code Exchange (PCKE)](https://auth0.com/docs/get-started/authentication-and-authorization-flow/authorization-code-flow-with-proof-key-for-code-exchange-pkce) OAuth flow provided by Spotify. playlistix will store the issued Access and Refresh Tokens in the browser's local storage for later use.

## Setup

tbd

## Data structures

playlistix exports Spotify playlists to JSON files. An output JSON file will have following structure:

```json
{
    "structure": "playlistix-playlist-r1",
    "name": "<playlist name>",
    "tracks": [
        {
            "spotifyId": "<track id from spotify>",
            "name": "<track name>",
            "artist": "<artist name>"
        }
    ]
}
```