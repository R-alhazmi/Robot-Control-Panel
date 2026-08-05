# Robot Control Panel

## Table of Contents
* [Repository Contents](#repository-contents)
* [Task Overview](#task-overview)
* [Live Demo](#live-demo)
* [Features & User Interface](#features--user-interface)
* [Tech Stack](#tech-stack)
* [Code Implementation & Design Structure](#code-implementation--design-structure)
* [How to Run](#how-to-run)
* [Expected Results](#expected-results)

---

## Repository Contents
* **index.html** – The main front-end interface containing the HTML structure, modern CSS styling, interactive control buttons, and Web Speech API logic.
* **update_command.php** – The backend script responsible for receiving command requests, mapping them to single-character instructions, and updating the database.
* **get_state.php** – The backend script used to fetch the current robot state and update timestamp from the database.
* **db.php** – The central database connection configuration file.
* **README.md** – Main project documentation file.

---

## Task Overview
This task was developed as part of the Smart Methods Training Program (July 2026).  
The primary objective is to design and build a clean, modern, and user-friendly web interface for a **Robot Control Panel**. The interface enables users to control a robot's movement (Forward, Backward, Left, Right, and Stop) either manually through an intuitive directional grid layout or hands-free via integrated browser-based **Voice Commands**.

---

## Live Demo
You can access and test the live version of the control panel here:  
🔗 **https://robot-control-panel.infinityfreeapp.com/**

---

## Features & User Interface
* **Modern Aesthetic:** Built with a soft-toned gradient background, custom-styled circular directional buttons, and a distinct soft-pink "Stop" button.
* **Responsive Control Pad:** Enlarged grid-based layout for smooth interaction and clear visual hierarchy without heavy container boxes.
* **Voice Control Integration:** Utilizes the Web Speech API to allow users to control the robot using spoken commands mapped via an optimized keyword dictionary.
* **Live Status Feedback:** An isolated status indicator box that updates dynamically to show connection states, recognized speech, and execution success or error messages.

---

## Tech Stack
* **Front-End:** HTML5, CSS3 (Flexbox, CSS Grid, Custom Shadows & Borders), JavaScript (Fetch API, Web Speech API).
* **Back-End:** PHP (`update_command.php`, `get_state.php`, `db.php`).
* **Database:** MySQL.
* **Hosting Platform:** InfinityFree.

---

## Code Implementation & Design Structure
* **Layout Design:** Styled using a CSS Grid container for the directional pad (`.control-pad`), ensuring precise alignment of the forward, backward, left, right, and stop buttons.
* **Voice Recognition Logic:** Implemented using `window.SpeechRecognition` with a modular command dictionary to capture and map spoken inputs efficiently.
* **Asynchronous Communication:** Uses JavaScript's `fetch` API via POST requests to transmit string-based commands securely to the backend without reloading the page.

---

## How to Run
1. Upload all project files (`index.html`, `update_command.php`, `get_state.php`, and `db.php`) to your web hosting server (e.g., InfinityFree).
2. Ensure your MySQL database contains the required table structure (`robot_state` with `id = 1`).
3. Open the deployed URL in a modern web browser (Google Chrome is recommended for full Web Speech API support).
4. Allow microphone permissions when prompted if you intend to use the voice command feature.
5. Click any directional button or use the **Voice Command** button to operate and control the robot.

---

## Expected Results
When interacting with the control panel:
* Clicking any directional or stop button instantly updates the status box with a success message and transmits the corresponding character command (`f`, `b`, `l`, `r`, `S`) to the database.
* Speaking a command into the microphone accurately recognizes the phrase, displays it in the status box, and sends the matching instruction to the server.
