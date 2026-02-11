# Valentine's Day Interactive Experience 💝

A romantic, multi-scene single-page application featuring games, puzzles, and sweet moments - all built with vanilla HTML, CSS, and JavaScript.

## 🎮 Experience Flow

1. **Initial Ask** - Playful "Will you be my Valentine?" with a moving "No" button
2. **Maze Game** - Navigate a heart through a maze to reach "ME"
3. **Heart Catcher** - Catch falling hearts for 120 seconds to earn points
4. **4×4 Puzzle** - Solve a sliding puzzle to reveal your special image
5. **Final Question** - One last romantic ask with confetti celebration

## ✨ Features

### Design
- 🎨 Soft pink romantic theme throughout
- 💕 Floating hearts background animation
- 🎵 Background romantic music with mute/unmute toggle
- 🎊 Confetti celebrations at key moments
- 📱 Fully responsive (mobile & desktop)
- 🌊 Smooth fade transitions between scenes

### Interactivity
- ⌨️ Keyboard controls (arrow keys)
- 👆 Touch/swipe support for mobile
- 🎯 Collision detection
- 🧩 Puzzle solving logic
- ⏱️ Timer and score tracking

### Games
- **Maze**: Navigate through obstacles with playful messages when hitting walls
- **Heart Catcher**: Three types of hearts (normal +1, golden +3, broken -2 points)
- **Puzzle**: 4×4 sliding puzzle with custom image upload support

## 🚀 Quick Start

### Option 1: GitHub Pages (Recommended)

1. **Create a new repository** on GitHub

2. **Upload the file**:
   - Rename `valentine.html` to `index.html`
   - Upload to your repository

3. **Enable GitHub Pages**:
   - Go to Settings → Pages
   - Source: Deploy from branch `main`
   - Folder: `/ (root)`
   - Save

4. **Access your site**:
   - Your site will be live at: `https://yourusername.github.io/repository-name/`

### Option 2: Local Testing

Simply open `valentine.html` in any modern web browser.

## 🎨 Customization Guide

### 1. Replace the Puzzle Image

**Option A: Upload via the webpage**
- When you reach Scene 4, click "📷 Upload Your Image"
- Select any square image (works best at 400×400px or larger)

**Option B: Set a default image in code**

Find this line (around line 1078):
```javascript
const defaultPuzzleImage = 'data:image/svg+xml,...';
```

Replace with your image URL or file path:
```javascript
const defaultPuzzleImage = 'path/to/your/image.jpg';
```

### 2. Change Background Music

Find this line (around line 228):
```html
<source src="https://assets.mixkit.co/music/preview/mixkit-romantic-piano-939.mp3" type="audio/mpeg">
```

Replace with your own music file:
```html
<source src="your-music.mp3" type="audio/mpeg">
```

**Note**: Upload your music file to the repository and use relative path: `your-music.mp3`

### 3. Personalize Messages

#### Initial Ask Message
Line ~237:
```html
<h1>💝 Will you be my Valentine? 💝</h1>
```

#### Maze Completion Message
Line ~665:
```javascript
messageDiv.textContent = '💕 You always find your way back to me! 💕';
```

#### Heart Catcher End Message
Lines ~831-840 - Edit the score message and prize amount

#### Puzzle Completion Message
Line ~1163:
```html
<div>You put us back together perfectly!</div>
```

#### Final Scene Messages
Lines ~1185-1186 and ~1226-1231

### 4. Adjust Game Difficulty

#### Maze Complexity
Edit the maze pattern (lines ~597-606):
- `1` = walkable path
- `0` = wall

#### Heart Catcher Duration
Line ~728:
```javascript
let timeLeft = 120; // Change to any number of seconds
```

#### Heart Spawn Rate
Line ~741:
```javascript
gameInterval = setInterval(spawnHeart, 800); // Change 800 to adjust (milliseconds)
```

#### Puzzle Size
Line ~864:
```javascript
const PUZZLE_SIZE = 4; // Change to 3 for 3×3, 5 for 5×5, etc.
```

**Note**: Also update grid-template-columns in CSS (line ~388):
```css
grid-template-columns: repeat(4, 1fr); /* Match PUZZLE_SIZE */
```

### 5. Color Scheme

All colors are defined as CSS variables at the top (lines ~14-20):
```css
:root {
  --pink-light: #FFE5EC;
  --pink-medium: #FFB3C6;
  --pink-dark: #FF8FAB;
  --pink-accent: #FF6B9D;
  --white: #FFFFFF;
  --text-dark: #5D3A4A;
  --shadow: rgba(255, 107, 157, 0.3);
}
```

Change these values to customize the entire color scheme!

## 🎯 Browser Compatibility

Works on all modern browsers:
- ✅ Chrome/Edge (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

**Note**: Background music autoplay may be blocked by some browsers. Users can click the 🔊 button to enable.

## 📱 Mobile Controls

- **Maze**: Swipe up/down/left/right to move
- **Heart Catcher**: Drag the basket with your finger
- **Puzzle**: Tap tiles to move them

## 🎵 Music Attribution

Default music: "Romantic Piano" from Mixkit (royalty-free)
- You can replace with any royalty-free music
- Recommended sources: Pixabay, YouTube Audio Library, Free Music Archive

## 🖼️ Image Recommendations

For best puzzle experience:
- Use square images (400×400px or larger)
- Choose images with distinct features/colors
- Avoid plain or monochrome images
- Personal photos work great!

## 🐛 Troubleshooting

**Music not playing?**
- Some browsers block autoplay
- Click the 🔊 button in the top-right
- Click anywhere on the page to trigger audio

**Puzzle not shuffling?**
- The puzzle auto-shuffles after 0.5 seconds
- Click "🔀 Shuffle" button to shuffle again

**Touch controls not working?**
- Make sure you're using a modern mobile browser
- Try refreshing the page

**Game running slowly?**
- Reduce floating hearts (line ~362, change interval from 500 to 1000)
- Use a smaller puzzle image

## 💡 Tips for Best Experience

1. **Test on Mobile**: The experience is designed to work beautifully on both desktop and mobile
2. **Choose the Right Music**: Pick something soft and romantic to match the vibe
3. **Personal Touches**: Use your own photos in the puzzle for extra sentimentality
4. **Share the Link**: Send the GitHub Pages link before Valentine's Day!

## 📝 File Structure

```
valentine.html          # Single-page application (all code in one file)
your-music.mp3         # (Optional) Your custom background music
your-puzzle-image.jpg  # (Optional) Your default puzzle image
```

## 🎨 Advanced Customization

### Add More Playful Messages

Edit the arrays:
- **No button messages** (line ~579)
- **Maze wall messages** (line ~593)

### Change Heart Types in Catcher

Edit the heart types array (lines ~754-758):
```javascript
const types = [
  { emoji: '❤️', points: 1, prob: 0.6 },   // 60% chance
  { emoji: '💛', points: 3, prob: 0.25 },  // 25% chance (golden)
  { emoji: '💔', points: -2, prob: 0.15 }  // 15% chance (broken)
];
```

### Adjust Animation Speeds

- **Floating hearts**: Line ~52 (animation-duration)
- **Falling hearts**: Line ~754 (animationDuration)
- **Scene transitions**: Line ~154 (transition duration)

## 📄 License

Free to use for personal romantic purposes! Share the love! 💕

---

## 🚀 Deployment Checklist

- [ ] Rename `valentine.html` to `index.html`
- [ ] Add custom music file (optional)
- [ ] Add default puzzle image (optional)
- [ ] Customize messages with names/personal touches
- [ ] Test on mobile and desktop
- [ ] Push to GitHub
- [ ] Enable GitHub Pages
- [ ] Test the live link
- [ ] Share with your Valentine! 💖

---

**Made with ❤️ for making Valentine's Day special**

Got questions or want to add features? The code is well-commented and organized by scene!
