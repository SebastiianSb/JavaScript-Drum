# JavaScript Drum Kit 🎵🥁

An interactive web-based drum kit that lets you play drum sounds using your keyboard. Built with vanilla JavaScript, HTML, and CSS.

![JavaScript Drum Kit](https://fav.farm/guitar)

## ✨ Features

- **9 Interactive Drum Pads** - Map to keyboard keys A through L
- **Real-time Audio Playback** - Instant sound response
- **Visual Feedback** - Animated keys when pressed
- **Neon Aesthetic** - Dark theme with glowing effects
- **Zero Dependencies** - Pure HTML, CSS, and JavaScript

## 🎹 Key Mappings

| Keyboard Key | Sound    | Description       |
|--------------|----------|-------------------|
| A            | clap     | Hand clap sound   |
| S            | hihat    | Hi-hat cymbal     |
| D            | kick     | Bass drum         |
| F            | openhat  | Open hi-hat       |
| G            | boom     | Deep boom/tom     |
| H            | ride     | Ride cymbal       |
| J            | snare    | Snare drum        |
| K            | tom      | Low tom           |
| L            | tink     | High tink/bell    |

## 🚀 Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- Keyboard with A-L keys

### Running the Project

1. **Open the project folder**
   ```bash
   cd "/home/sebastian/pCloudDrive/Programming/JavaScript/01 - JavaScript Drum Kit"
   ```

2. **Launch in browser**
   
   Simply open `index.html` in your web browser:
   ```bash
   # Using Firefox
   firefox index.html
   
   # Or open with default browser
   xdg-open index.html
   ```

3. **Start Playing!**
   - Press any of the keys (A, S, D, F, G, H, J, K, L) on your keyboard
   - Each key press triggers the corresponding drum sound
   - Enjoy creating your own beats!

## 📁 Project Structure

```
01 - JavaScript Drum Kit/
├── index.html              # Main HTML structure
├── style.css               # Styling and animations
├── README.md               # This file
├── electric-guitar-with-neon-light-still-life.jpg  # Background image
└── sounds/                 # Audio files
    ├── boom.wav
    ├── clap.wav
    ├── hihat.wav
    ├── kick.wav
    ├── openhat.wav
    ├── ride.wav
    ├── snare.wav
    ├── tink.wav
    └── tom.wav
```

## 🛠️ Technical Details

### Core Technologies
- **HTML5**: Semantic markup with data attributes for key-sound mapping
- **CSS3**: Flexbox layout, transitions, transforms, box-shadow effects
- **JavaScript (ES6)**: Event listeners, DOM manipulation, audio control

### How It Works

1. **Event Listening**: The `keydown` event triggers the `playSound()` function
2. **Audio Selection**: Uses `querySelector` with `data-key` attribute to find matching audio
3. **Sound Playback**: Resets `audio.currentTime = 0` for rapid replay, then calls `audio.play()`
4. **Visual Feedback**: Adds `.playing` class for CSS animation, removes on `transitionend`

### Key Functions

```javascript
// Plays sound and adds visual effect
function playSound(element) {
    const audio = document.querySelector(`audio[data-key="${element.keyCode}"]`);
    const key = document.querySelector(`.key[data-key="${element.keyCode}"]`);
    if(!audio) return;
    
    audio.currentTime = 0;
    audio.play();
    key.classList.add('playing');
}

// Removes visual effect after transition
function removeTransition(element) {
    if(element.propertyName !== 'transform') return;
    this.classList.remove('playing');
}
```

## 🎨 Visual Features

- **Neon Glow Effects**: Red box-shadow and text-shadow when keys are active
- **Smooth Animations**: 0.07s ease transitions for responsiveness
- **Background**: Full-cover guitar still life image
- **Responsive Design**: Flexbox centering for any screen size

## 📝 Notes

- Press and hold a key for rapid-fire sounds
- The audio automatically rewinds to start on each keypress
- Works offline once loaded (no server required)

## 📄 License

This project is open source and available for personal and educational use.

## 🙏 Acknowledgments

- Sound samples from Wes Bos's JavaScript 30 course
- Inspired by classic drum machines and pad controllers

---

Created by Juan Sebastian Andrade Sanchez 
Made with ❤️ using vanilla JavaScript


