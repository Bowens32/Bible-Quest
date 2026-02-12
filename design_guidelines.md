# Bible App Design Guidelines

## Brand Identity

**Purpose**: A reverent yet engaging Bible app that makes scripture accessible through reading and audio, while making learning enjoyable through progressive trivia.

**Aesthetic Direction**: Editorial/refined with warmth. Think of a beautifully typeset book brought to digital life—generous whitespace, elegant typography, subtle sepia tones that evoke traditional scripture without feeling dated. The trivia element adds playful energy through animated interactions, not visual clutter.

**Memorable Element**: The progression system—visualizing your journey through scripture as you advance through trivia chapters creates a sense of accomplishment and spiritual growth.

## Navigation Architecture

**Root Navigation**: Tab Bar (3 tabs)
- **Read** (Book icon): Scripture reading and audio
- **Play** (center, Trophy icon): Trivia game center position emphasizes core engagement
- **Profile** (User icon): Progress, settings, account

**Auth Required**: Yes (for trivia progress sync, leaderboards, cross-device continuity)
- SSO: Apple Sign-In (iOS), Google Sign-In (Android)
- Login/signup with privacy policy and terms placeholders

## Screen Specifications

### Onboarding Flow (Stack-only, first launch)
**Welcome Screen**
- Full-screen illustration (welcome-to-scripture.png) showing open book with soft light
- "Read. Listen. Learn." tagline
- "Get Started" button at bottom (above safe area + Spacing.xl)

### Read Tab Stack

**Book Selection Screen** (initial screen)
- **Header**: Default, transparent, title "Holy Bible"
- **Layout**: Scrollable, top inset: headerHeight + Spacing.xl, bottom: tabBarHeight + Spacing.xl
- **Content**: Two sections (Old Testament, New Testament) with cards for each book showing book name and chapter count
- **Empty state**: N/A (always populated)

**Chapter Selection Screen**
- **Header**: Default, book name as title, back button
- **Layout**: Scrollable grid (3 columns), standard insets
- **Content**: Numbered cards for each chapter, visual indicator showing completed trivia chapters (subtle checkmark)

**Reading Screen**
- **Header**: Custom transparent header with chapter navigation arrows (left/right), audio play button (right), back button
- **Layout**: Scrollable, generous padding, top inset: headerHeight + Spacing.xl, bottom: tabBarHeight + Spacing.xl
- **Content**: Verse-by-verse text with verse numbers in margin
- **Footer**: Fixed audio controls bar (play/pause, 15s back/forward, speed control) appears when audio active

### Play Tab Stack

**Trivia Hub Screen**
- **Header**: Default, transparent, title "Trivia Journey"
- **Layout**: Scrollable, top inset: headerHeight + Spacing.xl, bottom: tabBarHeight + Spacing.xl
- **Content**: 
  - Progress card showing current book/chapter
  - "Continue" CTA button (primary color, prominent)
  - Leaderboard preview (top 3 players)
  - Personal stats cards (total correct answers, current streak)
- **Empty state**: If no progress, show (trivia-start.png) with "Begin your journey through Genesis"

**Trivia Question Screen** (Modal)
- **Header**: Custom header with chapter title, close button (X), progress bar showing question # of 10
- **Layout**: Not scrollable, centered content
- **Content**:
  - Question text (large, readable)
  - 4 answer buttons (Card style)
  - Timer indicator (optional, subtle)
- **Feedback**: Correct answers turn green with checkmark, incorrect show red with correct answer highlighted

**Trivia Results Screen** (Modal)
- **Header**: Custom, "Chapter Complete" title, close button
- **Layout**: Centered content
- **Content**: 
  - Illustration (chapter-complete.png)
  - Score (X/10)
  - "Next Chapter" button or "Replay Chapter"
  - XP/progress earned

**Leaderboard Screen**
- **Header**: Default, title "Leaderboard", back button
- **Layout**: Scrollable list
- **Content**: Ranked list with avatars, names, total score
- **Empty state**: (empty-leaderboard.png) "Be the first to complete chapters"

### Profile Tab Stack

**Profile Screen**
- **Header**: Default, transparent, title "Profile", settings icon (right)
- **Layout**: Scrollable, top inset: headerHeight + Spacing.xl, bottom: tabBarHeight + Spacing.xl
- **Content**:
  - User avatar and display name (editable)
  - Progress overview (books completed, chapters read, trivia score)
  - Achievement badges (if earned)
  - Reading streak calendar
- **Empty state**: N/A (always shows user data)

**Settings Screen**
- **Header**: Default, title "Settings", back button
- **Layout**: Scrollable form
- **Content**: Audio settings (speed, voice), notifications, theme toggle (light/sepia/dark), account management (nested), privacy policy, terms

## Color Palette

- **Primary**: #8B6F47 (warm bronze, evokes aged parchment and tradition)
- **Secondary**: #C19A6B (lighter bronze for accents)
- **Background**: #FAF7F2 (warm off-white, like aged paper)
- **Surface**: #FFFFFF (pure white for cards)
- **Text Primary**: #2C2416 (deep brown, softer than black)
- **Text Secondary**: #6B5D4F (muted brown)
- **Correct**: #4A7C59 (muted sage green)
- **Incorrect**: #A84448 (muted burgundy)
- **Accent**: #D4AF37 (gold for achievements)

## Typography

- **Primary Font**: EB Garamond (Google Font) - elegant serif for scripture text
- **Secondary Font**: Inter (system) - clean sans-serif for UI elements, buttons
- **Scale**:
  - Display (32px, Bold, Inter): Screen titles
  - Heading (24px, Semibold, Inter): Section headers
  - Scripture (18px, Regular, EB Garamond): Bible text
  - Body (16px, Regular, Inter): General UI text
  - Caption (14px, Regular, Inter): Metadata, verse numbers

## Visual Design

- Cards have subtle shadow (shadowOffset: 0,2, opacity: 0.08, radius: 4)
- Floating action buttons use shadowOffset: 0,2, opacity: 0.10, radius: 2
- Use Feather icons throughout
- Transitions are gentle (fade, slide) not abrupt
- Pressed states: reduce opacity to 0.7 for buttons

## Assets to Generate

1. **icon.png** - App icon: Open book with subtle golden glow
2. **splash-icon.png** - Same as icon, centered during launch
3. **welcome-to-scripture.png** - Open book with soft divine light rays, warm tones (Onboarding Welcome Screen)
4. **trivia-start.png** - Stylized path/journey beginning at Genesis, invitation to start (Trivia Hub empty state)
5. **chapter-complete.png** - Celebration illustration, golden checkmark with confetti (Trivia Results Screen)
6. **empty-leaderboard.png** - Empty podium with encouraging message (Leaderboard empty state)
7. **avatar-1.png** through **avatar-4.png** - User avatar options: simple, respectful designs (Profile customization)