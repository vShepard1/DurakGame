# Changelog

All notable changes to Telegram Mini App "Дурак" will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2025-08-29

### Added
- **Complete Card Game "Дурак" Implementation**
  - **Core Game Logic**: Full implementation of Russian "Дурак" card game rules
  - **36-Card Deck**: Standard deck with cards 6-A in all suits (♠♣♦♥)
  - **Trump System**: Automatic trump suit determination and visual indicators (★)
  - **Attack/Defense Mechanics**: Proper card beating rules (trump beats non-trump, higher rank beats lower in same suit)
  - **Card Throwing Logic**: Ability to throw additional cards of matching ranks during attack phase
  - **Round Completion**: Automatic card drawing after each round completion

- **Interactive User Interface**
  - **Clickable Card System**: Click cards to play them during your turn
  - **Dynamic Game Display**: Real-time updates of game state and card positions
  - **Action Buttons**: "Взять карты" (Take Cards) and "Бито/Хватит" (Enough/Beat) buttons with context-aware visibility
  - **Game Status Indicators**: Current player, trump suit, remaining deck count display
  - **Table Card Display**: Visual representation of attack/defend card pairs with rotation effects

- **Smart Card Organization**
  - **Automatic Hand Sorting**: Cards sorted by suit (♠♣♦♥) then by rank (6-A)
  - **Trump Cards Positioning**: Trump cards displayed on the right side of hand
  - **Visual Trump Indicators**: Gold star (★) overlay on trump cards
  - **Color Coding**: Red cards (♦♥) and black cards (♠♣) properly colored

- **AI Opponent System**
  - **Strategic Decision Making**: AI can attack, defend, and decide when to throw additional cards
  - **Intelligent Card Selection**: AI prioritizes appropriate cards for attack/defense
  - **Dynamic Card Taking**: AI automatically takes cards when unable to defend
  - **Throw Decision Logic**: AI has 60% probability to throw additional cards when possible

- **Telegram Mini App Integration**
  - **Telegram Web App API**: Full integration with Telegram's Mini App framework
  - **Theme Adaptation**: Automatic adaptation to Telegram's light/dark themes
  - **User Information Display**: Shows Telegram user's name and language
  - **Main Button Integration**: Dynamic main button for game control
  - **Haptic Feedback**: Vibration support for enhanced user experience

- **Responsive Design & Animations**
  - **PT Mono Typography**: Monospace font throughout the application for retro gaming feel
  - **Card Hover Effects**: Subtle elevation effects on card hover
  - **Overlapping Opponent Cards**: Opponent's cards visually stack with -25px margin
  - **Clean Card Animations**: Smooth transitions without distracting floating animations
  - **Mobile-Optimized Layout**: Responsive design for various screen sizes

### Fixed
- **Game State Management**
  - **Proper Turn Switching**: Correct alternation between player and AI turns
  - **Card Drawing Timing**: Cards drawn only at end of complete rounds, not after individual moves
  - **Attack/Defense Role Management**: Proper role switching based on game outcomes
  - **Round Completion Logic**: Accurate detection of when rounds end (all cards beaten or taken)

- **AI Behavior Corrections**
  - **Card Taking Logic**: AI properly takes cards when unable to defend instead of returning cards to player
  - **Defense Mechanics**: AI correctly attempts to defend with appropriate cards
  - **Turn Completion**: Proper game flow when AI cannot continue attacking

- **Visual Display Issues**
  - **Dynamic Opponent Card Count**: Opponent card icons now match actual card count (not fixed at 6)
  - **Immediate Card Updates**: Player hand updates immediately after card drawing
  - **Consistent Card Sizing**: Cards maintain constant size regardless of hand size

- **Card Throwing Mechanics**
  - **Throw During Undefended Attacks**: Players can now throw additional cards even when opponent hasn't defended
  - **Proper Throw Validation**: Throwing limited to matching ranks of cards already on table
  - **Action Button Logic**: Correct button display ("Хватит"/"Бито") based on table state

### Technical Implementation
- **Game Engine**: Pure JavaScript implementation with modular game state management
- **Card Representation**: Object-based cards with suit, value, color, and weight properties
- **Deck Management**: Fisher-Yates shuffle algorithm for random card distribution
- **Win Condition Detection**: Automatic game end detection when deck is empty and player has no cards
- **Error Handling**: Robust validation for card plays and game state transitions

### User Experience
- **Intuitive Controls**: Simple click-to-play interface with helpful status messages
- **Clear Visual Feedback**: Color-coded cards, trump indicators, and game state displays
- **Smooth Gameplay Flow**: Minimal delays with strategic AI thinking pauses (1000ms)
- **Professional Interface**: Clean, distraction-free design focused on gameplay