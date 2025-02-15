My Pygame RPG
This repository contains a Python + Pygame RPG project that demonstrates the fundamentals of:

State machines (for managing different screens or game states)
Modular code and resource management
SQL-based save and load functionality
The game features a Maroon Screen state by default, but you can bypass it (once ready) and go straight to additional states (like A1).

Table of Contents
Features
Requirements
Installation
How to Run
Project Structure
Contributing
License
Features
Fixed 4:3 Aspect Ratio: The game is internally rendered at 800x600, then automatically scaled to the player’s window size.
Global Resources: A GlobalResources class handles all shared assets (images, sounds) and the DatabaseManager.
SQL Save System: Uses SQLite to store player data, ensuring easy save/load functionality.
State Manager: Manages different “screens” or “states” (e.g., the Maroon Screen, and eventually the main gameplay states).
Fullscreen Toggle: Press F at any time to switch between fullscreen and windowed modes.
Graceful Exit: Press ESC to quit, ensuring the database connection is closed properly.
Requirements
Python 3.7+
Pygame 2.0+
(Optional) Virtual Environment (recommended to avoid dependency conflicts)
If you plan to modify or extend the code, you may also want:

Git for version control
Any text editor or IDE of your choice (e.g., VS Code, PyCharm, etc.)
Installation
Clone or Download this repository:

bash
Copy
Edit
git clone https://github.com/YourUsername/MyPygameRPG.git
cd MyPygameRPG
Install Dependencies (ideally in a virtual environment):

bash
Copy
Edit
pip install pygame
If you have any other dependencies (like cx_Freeze or PyInstaller), add them here.

Check Python Version:

bash
Copy
Edit
python --version
It should be Python 3.7 or higher.

How to Run
Open a terminal (or command prompt) in the project folder.
Launch the main script:
bash
Copy
Edit
python main.py
The game window will appear:
Press ESC to quit.
Press F to toggle fullscreen.
Use your mouse to click on in-game buttons, which are converted to the internal 4:3 aspect ratio via the translate_mouse_position method.
Notes on Gameplay
By default, the game loads the Maroon Screen (from maroon_screen.py). You can modify the Game class to load different states when you’re ready (e.g., A1 or any other state file).
The SQL database file (game_data.db) will be automatically created in your project folder if it doesn’t exist yet.
Project Structure
plaintext
Copy
Edit
MyPygameRPG/
│
├─ main.py                  # Entry point (contains the Game class & main loop)
├─ SQLwithSaverLoader.py    # DatabaseManager for saving/loading player data
├─ global_resources.py      # Loads shared assets & references the DatabaseManager
├─ state_manager.py         # Handles transitions between states
├─ maroon_screen.py         # Example state (MaroonScreen)
├─ (Other state files)      # A1.py, A2.py, etc. for your future states
│
├─ assets/                  # Images, sound files, etc.
└─ game_data.db             # SQLite database (auto-created if missing)
main.py: Initializes everything, sets up the display, and starts the primary loop.
SQLwithSaverLoader.py: The core of the SQL saving/loading system.
global_resources.py: Holds references to images, sounds, and the shared DatabaseManager.
state_manager.py: A straightforward manager that calls update(), handle_events(), and render() on the current state.
maroon_screen.py: A demonstration “screen” or “state,” acting as a placeholder until you’re ready to load other states.
Contributing
Fork this repository.
Create a new branch for your feature/bug fix:
bash
Copy
Edit
git checkout -b feature-cool-improvement
Commit changes and push your branch:
bash
Copy
Edit
git commit -m "Add a cool improvement"
git push origin feature-cool-improvement
Open a Pull Request on GitHub, describing your changes.
We welcome bug reports, feature ideas, and code contributions.

License
This project is licensed under the MIT License. Feel free to adapt and use it in your own projects!

If you use this code in any derivative works, we’d love to hear about it—drop us a link so we can check it out and possibly showcase it!

Thank you for checking out our Pygame RPG! We hope this project inspires you to build awesome 2D games and keep experimenting with Python, Pygame, and SQL-based save systems. Have fun!
