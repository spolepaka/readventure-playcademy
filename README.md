# 📖 Readventure

**Turn Reading into Adventure** - A gamified reading comprehension game built for the Playcademy platform.

![Readventure](https://img.shields.io/badge/Platform-Playcademy-blue) ![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue) ![Vite](https://img.shields.io/badge/Vite-7.2-purple)

## 🎮 Overview

Readventure is an engaging reading comprehension game designed for 3rd graders. Students navigate through a space-themed tile board, reading passages and answering questions to progress through their learning journey.

### Key Features

- **🚀 PowerPath 100 Algorithm** - Adaptive question serving that adjusts difficulty based on student performance
- **🎯 Progressive Section Reveal** - Guiding questions reveal passage sections progressively, helping students focus
- **🏆 Gamified Experience** - Space-themed tile board with visual progress tracking
- **🔊 Sound Effects** - Engaging audio feedback for interactions (disabled during reading)
- **📊 Real-time Stats** - Mission Control panel showing score, accuracy, and progress

## 🛠️ Tech Stack

- **Framework**: TypeScript + Vite
- **Platform**: [Playcademy SDK](https://playcademy.net)
- **Styling**: CSS with custom animations
- **Data Format**: QTI (Question and Test Interoperability)

## 🚀 Getting Started

### Prerequisites

- [Bun](https://bun.sh/) (recommended) or Node.js 18+
- A Playcademy account (for deployment)

### Installation

```bash
# Clone the repository
git clone https://github.com/spolepaka/readventure-playcademy.git
cd readventure-playcademy

# Install dependencies
bun install

# Start development server
bun run dev
```

### Development

```bash
# Run development server
bun run dev

# Build for production
bun run build

# Deploy to Playcademy
bunx playcademy deploy
```

## 📁 Project Structure

```
readventure-playcademy/
├── src/
│   ├── game/
│   │   ├── SpaceReadingGame.ts  # Main game logic
│   │   ├── powerpath.ts         # PowerPath 100 algorithm
│   │   ├── tiles.ts             # Tile generation
│   │   └── confetti.ts          # Celebration effects
│   ├── utils/
│   │   ├── config-loader.ts     # Configuration loading
│   │   ├── qti-parser.ts        # QTI data parsing
│   │   └── sound-manager.ts     # Audio management
│   ├── styles/
│   │   └── main.css             # Game styles
│   └── main.ts                  # Entry point
├── public/
│   ├── assets/                  # Game images
│   ├── sounds/                  # Sound effects
│   ├── texts/                   # QTI content data
│   └── game-config.json         # Game configuration
├── index.html                   # Landing page
├── game.html                    # Game page
└── playcademy.config.js         # Playcademy configuration
```

## 🎯 PowerPath 100 Algorithm

The PowerPath 100 algorithm provides adaptive question serving:

| Student Accuracy | Expected Questions to Reach 100 |
|-----------------|--------------------------------|
| 100% | ~11 questions |
| 90% | ~14 questions |
| 80% | ~17 questions |
| 70% | ~24 questions |
| 60% | ~35 questions |

### How It Works

1. **Guiding Questions First** - Students answer guiding questions while reading progressively revealed sections
2. **Adaptive Difficulty** - Quiz questions are served based on current score:
   - Score 0-49: Easy questions
   - Score 50-89: Medium/Hard (75%/25% distribution)
   - Score 90-99: Hard questions only
3. **Smart Scoring** - Points increase for correct answers, decrease for incorrect (scaled by difficulty)

## 🔧 Configuration

Edit `public/game-config.json` to customize:

- Reading timer duration
- Pass threshold percentage
- Tile layout patterns
- Visual settings
- Content granularity mode

## 📝 Adding Content

Content is stored in QTI format in `public/texts/qti_grade_3_data.json`. Each article includes:

- Sections with guiding questions
- Quiz questions with difficulty levels
- Answer choices with correct/incorrect flags

## 🎨 Customization

### Themes

The game currently features a space theme. Key visual elements:

- Space-themed tile board background
- Animated blur effects for locked tiles
- Confetti celebration on completion

### Sounds

Sound effects are located in `public/sounds/`:
- `click.mp3` - Button clicks
- `hover.mp3` - Hover feedback
- `tile-select.mp3` - Tile selection
- `locked.mp3` - Locked tile feedback
- `success.mp3` - Completion celebration
- `whoosh.mp3` - Page transitions

## 📄 License

This project is part of the Playcademy games collection.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

---

Built with ❤️ for young readers everywhere.

