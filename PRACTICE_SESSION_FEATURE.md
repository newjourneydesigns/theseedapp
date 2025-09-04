# Practice Session Feature

## Overview
The Practice Session feature allows users to temporarily practice a different passage while preserving their current memorization progress. This enables users to:
- Take a break from their main passage to practice something else
- Work through all exercises with a different passage
- Return to their original passage with all progress intact

## How It Works

### Starting a Practice Session
1. User clicks the "Practice Session" button (visible when a main memorization plan is active)
2. A modal appears with a dropdown of available passages (excluding the current one)
3. User selects a passage and clicks "Start Practice"
4. The current plan state is saved to localStorage
5. A temporary practice plan is loaded
6. The page refreshes to show the practice passage

### During Practice Session
- A green "Practice Session" indicator appears at the top
- All normal exercises and drill modes are available
- Progress is tracked separately for the practice session
- The main "Practice Session" button is hidden
- An "End Practice" link is available in the indicator

### Ending Practice Session
- When all verses in the practice passage are completed, an "End Practice" modal automatically appears
- User can also manually end practice by clicking "End Practice" in the indicator
- User can choose to continue practicing or return to their main plan
- When returning to main plan, all saved state is restored
- The page refreshes to show the original passage with original progress intact

## Technical Implementation

### localStorage Keys Used
- `isPracticing`: Boolean flag indicating if user is in practice mode
- `savedMainPlan`: Backup of the original memorization plan
- `savedCurrentPassage`: Backup of the original current passage
- `savedCustomPassageText`: Backup of custom passage text (if applicable)
- `practicePassage`: Current practice passage key

### Key Classes and Methods
- `PracticeSession.saveMainPlanState()`: Saves current state before practice
- `PracticeSession.restoreMainPlanState()`: Restores original state after practice
- `PracticeSession.loadPracticePassage(passageKey)`: Loads a passage for practice
- `PracticeSession.isPracticing()`: Checks if currently in practice mode
- `PracticeSession.getAvailablePracticePassages()`: Gets passages available for practice

### UI Components
- Practice Session button (next to "Done For Today")
- Practice Session selection modal
- End Practice confirmation modal  
- Practice indicator banner (shown during practice)

## User Experience
1. **Seamless Transition**: Users can easily switch between main plan and practice
2. **Progress Preservation**: Original progress is never lost
3. **Visual Indicators**: Clear indication when in practice mode
4. **Flexible Completion**: Users can end practice at any time or let it auto-complete
5. **Exercise Compatibility**: All existing drill modes work in practice sessions

## Benefits
- Allows users to explore different passages without losing progress
- Provides variety in memorization practice
- Enables focused practice on specific passages
- Maintains engagement with the app through diverse content
- Preserves the integrity of the main memorization plan

The feature integrates seamlessly with the existing app functionality and provides a valuable addition to the memorization workflow.
