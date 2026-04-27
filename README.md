Slowburn - Dynamic Evolution Engine

Slowburn is a high-performance scripting system for AI Dungeon. It allows your NPCs to naturally "evolve" their personality, behavior, and loyalty based on how they interact with you.
Unlike standard story cards that can bloat the AI's memory, this engine uses a "Database" approach. It tracks a character's progress on a scale of 0 to 100 and injects only their current state into the Author's Note, keeping the AI focused and the context clean.

🚀 Installation
To install the engine, you will need to access the Scripting section of your AI Dungeon scenario.
    Open the Scripting Tab: Navigate to your scenario settings and select "Scripting."
    Slowburn is designed to be a "plug-and-play" evolution engine. Because it uses a centralized Library function, it is highly compatible with other popular scripting suites like Inner Self and Auto-Cards.

Follow these instructions to set up Slowburn as a standalone system or as part of a multi-script setup.

Option A: Standalone Installation (Slowburn Only)
If you are only using Slowburn: 
    1. Delete everything in the Library tab then copy and paste everything in "Put in LIBRARY" to the Library tab.
    2. Delete everything in the Input tab then copy and paste everything in "Put in INPUT" to the Input tab.
    3. Delete everything in the Output tab then copy and paste everything in "Put in "OUTPUT" to the Output tab.
Option B: Combined Installation (With Inner Self/Auto-Cards)
If you are using the Inner Self suite or other scripts:
    1. In the Library tab, copy everything in "Put in LIBRARY" and paste it below any other scripts in the Library tab.
    2. In the Input tab, copy everything in "Put in INPUT" and paste it below any other scripts in the Input tab.
    3. In the Output tab, copy everything in "Put in OUTPUT" and paste it below any other scripts in the Output tab.

🗃️ Story Card Setup
The engine reads all its data from your Story Cards. For the script to work, your cards must be formatted specifically within the Entry field.

1. The Headers
The script scans for the header Evolution Stages Part 1: to find your data. If you have many stages and hit the 2,000-character limit, simply create a second card starting with Evolution Stages Part 2:.

2. Configuration Settings
At the top of your Story Card Entry (inside Part 1), include these three lines:
    Character Name: The exact name of the NPC to track.
    Gain Rate: How much the level increases per positive interaction (e.g., 0.2).
    Drain Rate: How much the level decreases per negative interaction (e.g., 0.5).

3. Formatting the Stages
Each stage must follow the format: [Level Number]: [Stage Name] - [Description] towards ${What is your name?}.
Example Entry:

    Evolution Stages Part 1:
    Character Name: ${What is the characters name?}
    Gain Rate: 0.2
    Drain Rate: 0.5
    0: The Default - Standard, polite behavior towards ${What is your name?}.
    15: The Flirt - Active teasing and testing boundaries towards ${What is your name?}.
    ...

🧠 How It Works
This engine is designed to be "smart" so it doesn't break immersion or cheat the system.

🛡️ Anti-Spam Logic
The AI can sometimes be repetitive (e.g., "She sighs and sighs and sighs"). Our script uses Unique Word Detection. Even if the AI repeats a trigger word multiple times in one response, the evolution level will only change once for that word per turn.

🎯 Interaction Filtering
The engine only calculates "Vibe Checks" if the NPC is actually talking to or interacting with you. It scans the AI's output for the words "you" or "your." If the NPC is talking to a different character, the evolution level stays exactly where it is.

📝 Smart Author's Note Injection
The script manages your Author's Note automatically.
    It preserves any text you have manually written (like style or genre notes).
    It appends the Evolution State to the very end of the note.
    By placing the behavior at the end, the AI gives it maximum priority, ensuring the character acts exactly as their current level dictates.

🛠️ Tips for Success
    Triggers: You do not need complex keys. Set the Story Card triggers to the Character's Name.
    Variable Injection: Using ${What is your name?} in your descriptions allows the AI to automatically insert your character's name, making the instructions hyper-specific.
    Pacing: If the character is evolving too fast, lower the Gain Rate in your Story Card. If they are too forgiving, increase the Drain Rate.
