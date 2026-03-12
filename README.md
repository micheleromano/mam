# Music as Meditation 🧘

A calming mobile-first web app for meditation with music and wish-releasing rituals.

## Features

- **Meditation Music Player** — Browse and play calming solfeggio frequency tones (placeholder tracks ready to be replaced with your Spotify/uploaded music)
- **Wish Ritual** — Type or dictate a wish using voice-to-text, then release it with a beautiful particle animation and chime sound
- **Mobile-First Design** — Warm, calming aesthetic optimized for phones
- **Firebase Hosted** — Simple, free hosting

## Quick Start

### 1. Install Firebase CLI

```bash
npm install -g firebase-tools
```

### 2. Login to Firebase

```bash
firebase login
```

### 3. Create a Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Click "Add project"
3. Name it something like `music-as-meditation`
4. Disable Google Analytics (not needed)
5. Click "Create project"

### 4. Connect Your Project

Edit `.firebaserc` and replace `your-project-id` with your actual Firebase project ID:

```json
{
  "projects": {
    "default": "music-as-meditation"
  }
}
```

Or run:

```bash
firebase use --add
```

### 5. Deploy

```bash
firebase deploy
```

Your app will be live at: `https://your-project-id.web.app`

## Replacing Placeholder Music

The app currently generates meditation tones using the Web Audio API (solfeggio frequencies). To use real music:

### Option A: Upload MP3 Files

1. Place `.mp3` files in the `public/audio/` folder
2. Update the `songs` array in `index.html`:

```javascript
const songs = [
  { id: 1, title: "Your Song", artist: "Christian Stewart", duration: "5:00", seconds: 300, src: "audio/your-song.mp3" },
  // ...
];
```

3. Replace the `MeditationTone` class with a standard HTML5 Audio player

### Option B: Spotify Embed

Replace the tone generator with Spotify embeds using your artist ID. Add iframes to the song cards pointing to specific tracks.

## Project Structure

```
meditation-app/
├── firebase.json          # Firebase hosting config
├── .firebaserc            # Firebase project link
├── public/
│   ├── index.html         # Main app (single file)
│   ├── img/
│   │   └── mascot.png     # Meditating stick figure
│   └── audio/             # Place MP3 files here
└── README.md
```

## Tech Stack

- Vanilla HTML/CSS/JS (no framework dependencies)
- Web Audio API for generated meditation tones and chime sounds
- Web Speech API for voice dictation
- Canvas API for wish particle effects
- Firebase Hosting (free tier)

## Free Tier Limits

Firebase Hosting free tier includes:
- 10 GB storage
- 360 MB/day data transfer
- Custom domain support
- SSL certificate included

More than enough for a personal meditation app!
