# Scripture Journey - Bible App

## Overview
A Bible reading app with audio playback and interactive trivia. Users can browse all 66 books of the Bible, read scripture verse-by-verse with optional audio, and test their knowledge through progressive trivia challenges that unlock as they journey through the Bible.

## Features
- **Read**: Browse Old and New Testament books, select chapters, read verse-by-verse scripture
- **Audio**: Play/pause audio narration with speed controls (0.75x to 2x)
- **Trivia**: Multiple choice questions that progress through each book and chapter
- **Progress Tracking**: Track completed chapters, accuracy stats, and daily streaks
- **Profile**: View progress overview, settings, and app information

## Tech Stack
- **Frontend**: React Native with Expo
- **Navigation**: React Navigation (tabs + stack navigators)
- **State**: React Query + AsyncStorage for local persistence
- **Audio**: expo-audio
- **Styling**: Custom theme with warm bronze/sepia colors
- **Fonts**: EB Garamond for scripture text, system fonts for UI

## Project Structure
```
client/
├── App.tsx                    # Root app with providers
├── components/                # Reusable UI components
├── constants/theme.ts         # Colors, spacing, typography
├── data/
│   ├── bible.ts               # Bible book metadata (66 books)
│   ├── verses.ts              # Sample chapter content
│   └── trivia.ts              # Trivia questions
├── hooks/                     # Custom React hooks
├── lib/
│   ├── query-client.ts        # React Query setup
│   └── storage.ts             # AsyncStorage utilities
├── navigation/
│   ├── RootStackNavigator.tsx # Root stack with modals
│   ├── MainTabNavigator.tsx   # 3 tabs: Read, Play, Profile
│   ├── ReadStackNavigator.tsx # Book → Chapter → Reading
│   ├── PlayStackNavigator.tsx # Trivia hub
│   └── ProfileStackNavigator.tsx
└── screens/
    ├── BookSelectionScreen.tsx
    ├── ChapterSelectionScreen.tsx
    ├── ReadingScreen.tsx
    ├── TriviaHubScreen.tsx
    ├── TriviaQuestionScreen.tsx
    ├── TriviaResultsScreen.tsx
    └── ProfileScreen.tsx
```

## Design System
- **Primary**: #8B6F47 (warm bronze)
- **Secondary**: #C19A6B (lighter bronze)
- **Background**: #FAF7F2 (warm off-white)
- **Surface**: #FFFFFF (white cards)
- **Text**: #2C2416 (deep brown)
- **Correct**: #4A7C59 (sage green)
- **Incorrect**: #A84448 (burgundy)
- **Accent**: #D4AF37 (gold)

## Recent Changes
- Initial MVP implementation with reading, audio, and trivia features
- 3-tab navigation: Read, Play, Profile
- Sample Bible content for Genesis 1-3, Matthew 1, John 1
- Trivia questions for Genesis chapters 1-3, Matthew 1, John 1
- Progress tracking with AsyncStorage

## User Preferences
- Warm, editorial aesthetic inspired by traditional scripture
- Elegant typography for readability
- Progression-based trivia to encourage Bible study
