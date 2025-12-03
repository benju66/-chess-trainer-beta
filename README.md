♟️ App Profile: Chess Opening Trainer
Current Version: 3.0 (Coach Mode Update) Architecture: Single-File HTML/JS (Offline Capable, Mobile-First)

Description: A lightweight but powerful tool designed for players who want to build, manage, and memorize a custom chess repertoire. Unlike generic database apps, this tool focuses on "Coach Mode"—emphasizing the nature and purpose of every move rather than just the order. It features a "Brain" (Transposition detection) that automatically links identical board positions across different opening files, turning isolated lines into a connected web of knowledge.

Core Features:

Tree-Based Builder: Create complex branching repertoires with unlimited depth. Support for "Choice Points" where multiple playable options exist.

Active Recall Trainer: A practice mode that hides the upcoming moves, forcing the user to play from memory. It intelligently handles "Your Turn" vs. "Opponent's Turn" logic.

The "Brain" (Transposition Engine): A background system that analyzes every move using chess.js. If you reach a position you have studied in a completely different opening file, a Smart Badge appears, allowing you to jump instantly to that other file.

Mobile-First Design: Built specifically for vertical phone screens with large touch targets, sticky headers, and drawer-based navigation.

Portable Data: Uses simple JSON files for storage. You can edit them manually, share them, or host them on GitHub for raw URL importing.

🚀 V3.0 Release Summary: "The Coach Mode Update"
This update fundamentally changes how data is structured and entered, moving from simple text labels to structured chess data.

1. Data Standardization (The "Clean Slate")
New Fields: Replaced loose text inputs with two strict dropdowns for every move:

Status: (e.g., Mainline, Sideline, Novelty, Blunder).

Type: (e.g., Positional, Tactical, Prophylactic, Dynamic).

Auto-Migration: Includes a smart importer that automatically converts legacy V1/V2 files to the new V3 structure so no data is lost.

2. Progressive Input UI
Fast Path: The "Add Move" form is now compact by default, showing only the move input for rapid entry.

Sticky "Coach" Drawer: Tapping "Add Details ▾" opens a drawer for Status, Type, and Explanation. Crucially, this drawer is sticky—if you leave it open, it stays open for the next move, allowing for seamless detailed entry.

3. Integrated Reference Guide
Educational Modal: Added a clickable ⓘ icon next to the "Type" dropdown. This triggers a full-screen, mobile-friendly overlay defining complex terms like "Prophylactic" or "Quiet Move," helping beginners select the correct tag.

4. Smart Visuals
Auto-Coloring: The app now automatically assigns colors to cards based on the move type (e.g., "Tactical" moves turn Red, "Positional" moves turn Blue), eliminating manual color selection and ensuring visual consistency.

5. Stability & Logic Fixes (Carried from V2.2)
Robust Transposition Logic: Fixed self-referencing bugs where an opening would list itself as a match.

Visual Polish: Fixed unstyled white text areas to match the dark theme.
