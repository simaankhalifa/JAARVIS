JAARVIS Desktop Assistant - README

About the Project
JAARVIS is a voice and web-based personal AI assistant built in Python. It features a graphical user interface powered by Eel (HTML/CSS/JS frontend), hotword detection via Porcupine, system controls, YouTube playback, automated WhatsApp communication, and conversational AI capabilities using HugChat.

Key Features

* Voice Command Recognition: Listens to spoken instructions using Google Speech Recognition.
* Hotword Detection: Runs a background process listening for wake-words like "Jarvis" or "Alexa" using Picovoice Porcupine.
* Web-Based User Interface: Uses Eel to render a custom desktop interface in Microsoft Edge (`http://localhost:8000/index.html`).
* WhatsApp Integration: Automates text messaging, audio calls, and video calls via direct URL schemes and GUI automation (`pyautogui`).
* App & Web Launcher: Queries a local SQLite database (`jarvis.db`) to launch system applications or open web URLs.
* YouTube Integration: Automatically searches for and plays requested videos using `pywhatkit`.
* ChatBot Conversational AI: Uses `hugchat` to process general queries when a specific command is not recognized.

Project Structure

* `run.py`: Entry point for starting the application using Python multiprocessing (launches the assistant interface and hotword listener simultaneously).
* `main.py`: Sets up Eel, initializes the Web UI in Microsoft Edge, and plays start sounds.
* `command.py`: Handles speech-to-text input, text-to-speech output using `pyttsx3`, and command routing.
* `features.py`: Contains core engine functionalities including app opening, YouTube search, hotword processing, WhatsApp automation, and chatbot responses.
* `db.py`: Database setup file for managing tables (`sys_command`, `web_command`, `contacts`).
* `helper.py`: Utility functions for string manipulations and regex extraction.

Technologies & Libraries Used

* Python 3
* Eel (Python-Web frontend binding)
* SpeechRecognition & pyttsx3 (Voice processing & Speech synthesis)
* pvporcupine & PyAudio (Hotword detection)
* PyAutoGUI & PyWhatKit (Automation)
* HugChat (AI Chatbot module)
* SQLite3 (Local storage for system paths and contact data)

Setup & Installation

1. Clone the repository:
git clone [https://github.com/simaankhalifa/JAARVIS.git](https://www.google.com/search?q=https://github.com/simaankhalifa/JAARVIS.git)
cd JAARVIS
2. Create and activate a virtual environment:
python -m venv venv
For Windows: venv\Scripts\activate
For Mac/Linux: source venv/bin/activate
3. Install requirements:
pip install -r requirements.txt
4. Configure Database and Contacts:
Initialize the database structure by running:
python db.py

Running the Application
Run `run.py` to launch both the main Eel web interface and the background hotword listener simultaneously:

python run.py
