♟️ Chess Opening Trainer V4.0
"The Coach Mode Update"

A single-file, mobile-first web application for building, memorizing, and connecting your chess repertoire.

🚀 What is New in V4.0?
Version 4.0 introduces the "Universal Tree" Architecture.

Unified Structure: We removed the complex distinction between "Linear Responses" and "Branching Choices." Now, every move is a child node. This makes the app faster, more robust, and significantly easier for AI tools to generate content for.

Universal Migrator: A built-in engine that automatically converts your old V1, V2, and V3 JSON files into the new V4 format upon upload. You lose nothing.

Coach Mode Data: Standardized fields for "Status" (e.g., Mainline) and "Type" (e.g., Tactical), replacing unstructured text labels.

✨ Key Features
1. The "Coach Mode" Builder
Progressive Input: The "Add Move" form is fast and compact by default.

Sticky Details Drawer: Tap "Add Details ▾" to reveal the Coach fields (Status, Type, Explanation). This drawer stays open for rapid entry of detailed moves.

Reference Guide: A built-in clickable ⓘ icon opens a full-screen mobile modal defining complex terms like "Prophylactic" or "Dynamic" so you always pick the right label.

2. Smart Visuals
Auto-Coloring Cards: The interface automatically assigns colors to moves based on their type:

🔴 Red: Tactical / Forcing

🔵 Blue: Positional / Strategic / Quiet

🟢 Green: Defensive / Prophylactic

🟣 Purple: Dynamic

3. The "Brain" (Transposition Engine)
Cross-File Linking: If you reach a position in your French Defense file that you have also studied in your English Opening file, a purple "Transposition" badge appears.

Smart Filtering: The badge only appears if the match is in a different file, preventing the app from telling you "This position is found in the current file."

📂 V4.0 JSON Data Structure
V4.0 uses a strict Array-Only structure. The response object has been deprecated.

The Golden Rule: Every move—whether it is a single reply or a list of variations—must be inside a children array.

JSON

{
  "name": "Opening Name",
  "color": "white",
  "startingMoves": "1. e4",
  "tree": {
    "id": "root",
    "move": "1. e4",
    "player": "white",
    "status": "Mainline",
    "type": "Positional/Strategic",
    "explanation": "Controls the center.",
    "children": [  <-- ALWAYS AN ARRAY
      {
        "id": "c1",
        "move": "1... e5",
        "children": [  <-- ALWAYS AN ARRAY
           { "id": "c2", "move": "2. Nf3", "children": [] }
        ]
      }
    ]
  }
}
🤖 AI Generation Instructions
To generate new opening files using a Gemini Gem, paste these instructions into your "Chess Coach Architect" custom Gem.

System Instructions:

Plaintext

You are the "Chess Coach Architect." Your specific purpose is to generate valid JSON files for the "Chess Opening Trainer V4.0" application.

### OUTPUT FORMAT
- You must output raw JSON code only. No markdown formatting (no ```json blocks).
- Validate all JSON before outputting to ensure no trailing commas.

### 1. THE GOLDEN RULE (V4.0 ARCHITECTURE)
**Everything is a Child.**
- Do NOT use the `response` object.
- Do NOT use the `choices` array.
- Every move node—whether it is a single reply or a list of variations—must be inside a `children` array.

### 2. DATA INTEGRITY RULES
**A. Status & Type (Strict Enums):**
- *Status:* "Mainline", "Sideline", "Novelty", "Blunder", "Mistake", "Theoretical"
- *Type:* "Positional/Strategic", "Tactical", "Defensive/Prophylactic", "Dynamic", "Forcing", "Quiet"

**B. Coach Mode Explanations:**
- Every node must have an `explanation` string answering "Why?" (e.g., "Prevents the pin.").

**C. Player Perspective:**
- If User is WHITE: Root is White. Root `children` are Black.
- If User is BLACK: Root is White (Opponent). Root `children` are Black (User).

### 3. FORMATTING RULES
- **Wrappers:** Always wrap the tree in the full object (`name`, `color`, `description`, `tree`).
- **Notation:** Always include move numbers (e.g., "1. e4", "1... e5").
- **Escaping:** If an explanation contains quotes, use single quotes (e.g., "The 'French Bishop' problem") to avoid syntax errors.
📲 How to Install (Mobile)
Save the V4.0 source code as index.html on a computer.

Email the file to yourself or upload it to Google Drive/iCloud.

Open the file on your phone. It runs instantly in the browser—no app store required.
