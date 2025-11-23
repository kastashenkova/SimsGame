# Sims NaUKMA

A life simulation game based on student experience at NaUKMA (National University of Kyiv-Mohyla Academy) built with Java Swing.

## Features

- **Interactive Game World**: Explore campus with buildings, cafes, and study locations
- **Student Life Simulation**: Manage hero's activities, studies, and well-being
- **Test System**: Take academic tests with multiple-choice questions
- **Background Music**: Dynamic soundtrack for different game states
- **Custom UI**: Sims-style pink and blue color scheme
- **Building System**: Collision detection and interaction with campus buildings

## Game Mechanics

### Main Systems

**Hero Management**
- Stats tracking (energy, mood, knowledge)
- Activity scheduling
- Academic progress

**Testing System**
- Multiple-choice questions (А, Б, В, Г)
- Passing threshold: 10+ points
- Automatic grading
- Score-based marks (99 for 13+ points, scaled otherwise)

**Campus Buildings**
- **NaUKMA**: Main university building (430×200px)
- **Corpus 1**: Academic building (350×200px)
- **Cafe**: Student dining area (130×180px)
- **Shop**: Campus store (155×125px)
- **Ferris Wheel**: Entertainment (210×230px)

## Controls

**Main Menu:**
- **Нова гра**: Start new game
- **Налаштування**: Open settings
- **Вийти**: Exit application

**In-Game:**
- **Pause Button**: Access pause menu
- **Продовжити**: Resume game
- **Панель персонажки**: Return to character panel

**Test Interface:**
- **Наступне**: Next question
- **Завершити тест**: Finish test

## UI Components

### Color Palette

```java
SIMS_LIGHT_PINK:   #FFE9F3
SIMS_MEDIUM_PINK:  #FFD4DE
SIMS_TURQUOISE:    #40E0D0
SIMS_LIGHT_BLUE:   #ADD8E6
SIMS_DARK_TEXT:    #323232
```

### Screens

**WelcomeFrame**: Main menu with animated GIFs and background music  
**LoadingFrame**: Transition screen with loading animation  
**OptionsFrame**: Settings for music and game preferences  
**MainTestFrame**: Test interface with questions and results  
**GameBoard**: Main gameplay area with hero and buildings  
**DeDialogPanel**: Pause menu overlay

## Project Structure

```
├── gui/
│   ├── WelcomeFrame.java       # Main menu
│   ├── LoadingFrame.java       # Loading screen
│   ├── OptionsFrame.java       # Settings
│   ├── DeDialogPanel.java      # Pause menu
│   └── BackgroundPanel.java    # Custom background
├── Tests/
│   ├── MainTestFrame.java      # Test UI
│   ├── TestManager.java        # Question generation
│   └── Question.java           # Question model
├── mainstage/
│   ├── GameBoard.java          # Main game logic
│   ├── Building.java           # Building entity
│   └── BuildingManager.java    # Building setup
└── org.example/
    ├── MusicPlayer.java        # Audio manager
    ├── Hero.java               # Player character
    └── Discipline.java         # Academic subject
```

## Key Classes

### WelcomeFrame
- Main entry point
- Menu navigation
- Music initialization
- Button animations (hover/press effects)

### MainTestFrame
- Question display system
- Answer validation
- Score calculation
- Result panel with color-coded answers
- Retry functionality for failed tests

### GameBoard
- Game loop management
- Hero movement
- Building collision detection
- Pause/resume functionality

### BuildingManager
- Creates campus buildings
- Sets coordinates and dimensions
- Manages collision properties

### DeDialogPanel
- Pause overlay
- Quick navigation
- Settings access

## Test System Details

**Question Format:**
- 4 options per question (А, Б, В, Г)
- Single correct answer
- HTML-formatted results

**Scoring:**
- Pass: ≥10 points
- Fail: <10 points (retry offered)
- Excellent: ≥13 points (99 mark + Avtomat status)
- Regular: 10-12 points (scaled to 40-48 mark)

**Results Display:**
- ✓ Green for correct answers
- ✗ Red for incorrect selections
- Detailed answer review

## Audio System

**Background Music:**
- Welcome screen: `welcome.wav`
- Test screen: `testBack.wav`
- Toggleable via settings

**Sound Effects:**
- Button clicks
- Notification sounds

Uses singleton `MusicPlayer` for global audio control.

## Technical Details

**UI Framework:** Java Swing with FlatLaf look-and-feel  
**Graphics:** BufferedImage, ImageIcon for sprites  
**Threading:** SwingWorker for loading animations  
**Collision:** Rectangle-based bounding boxes  
**Layout:** BorderLayout, GridBagLayout, FlowLayout combinations

## Running the Game

```bash
javac gui/WelcomeFrame.java
java gui.WelcomeFrame
```

## Dependencies

- FlatLaf (Modern look-and-feel)
- Java Swing (GUI framework)
- Java AWT (Graphics and events)

## Features Highlight

✅ Animated welcome screen  
✅ Loading transitions  
✅ Interactive campus map  
✅ Academic test system  
✅ Score tracking  
✅ Music and sound effects  
✅ Pause functionality  
✅ Settings menu  
✅ Collision detection  
✅ Ukrainian localization

## Educational Value

Perfect for learning:
- Game loop implementation
- Swing UI design
- State management
- Audio integration
- Collision systems
- Testing frameworks

---

**Theme**: University life simulation  
**Style**: Sims-inspired aesthetics  
**Language**: Ukrainian interface
