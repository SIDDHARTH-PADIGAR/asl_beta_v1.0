## **asl_beta_v1.0: Sign Language Recognition App**

This is the **base model** and **first iteration** of the Sign Language Recognition App, focused on **efficiently identifying hand signs** using **OpenCV** and **MediaPipe**. This version serves as the MVP for a full-featured ASL learning tool. The primary goal is to accurately identify hand gestures from a webcam feed, providing a baseline for future enhancements.

---

### **Features:**
- **Hand Gesture Recognition**: Leverages **MediaPipe Hands** for real-time hand landmark detection.
- **Alphabet & Word Learning**: Practice individual ASL letters and build words.
- **Quiz Mode**: Engage with interactive challenges to test ASL knowledge.
- **Story Mode**: Learn ASL through simple sentences.
- **Text-to-Speech (TTS)**: Provides spoken feedback using **pyttsx3**.

---

### **Code Breakdown**

#### 1. **Imports & Dependencies**
This application uses:
- **OpenCV (`cv2`)**: For capturing webcam frames.
- **MediaPipe (`mp`)**: For detecting hand landmarks in real-time.
- **NumPy (`np`)**: For processing hand landmark data.
- **Pickle (`pickle`)**: To load a pre-trained machine learning model for gesture classification.
- **Threading (`threading`)**: Handles speech synthesis in parallel with the UI.
- **pyttsx3**: For converting text feedback into speech.

#### 2. **Application Modes**
The app offers four interactive modes:
- **`ALPHABET_PRACTICE`**: Learn ASL letters.
- **`WORD_BUILDER`**: Form words from ASL letters.
- **`QUIZ_MODE`**: Test ASL knowledge.
- **`STORY_TIME`**: Learn through interactive sentences.

#### 3. **Initializing the App**
The `SignLanguageApp` class:
- Loads the **hand tracking model** (MediaPipe).
- Loads the **pre-trained ASL recognition model** from `model.p`.
- Defines **ASL practice words** & stories.
- Sets up **video capture** with `cv2.VideoCapture(0)`.
- Initializes the **text-to-speech engine** (`pyttsx3`).

#### 4. **Text-to-Speech (TTS)**
The `speak_text()` method:
- Runs speech synthesis on a separate thread.
- Ensures previous speech is stopped before starting new speech.
- Provides **real-time feedback** to users.

#### 5. **User Interface (UI)**
- **`draw_ui_panel()`**: Renders mode selection buttons.
- **`draw_feedback_panel()`**: Displays real-time progress, including:
  - Target letters/words.
  - Current quiz scores.
  - Story text in story mode.

#### 6. **Hand Landmark Processing**
- **`process_hand_landmarks(frame)`**:
  - Converts the webcam frame to **RGB**.
  - Uses **MediaPipe** to detect hand landmarks.
  - Draws detected landmarks on-screen.
  - Prepares hand coordinates for **model prediction**.

---

### **How It Works:**

![chatuml-diagram (13)](https://github.com/user-attachments/assets/5ce94b5d-0b21-49f8-9c2a-abdd5c402388)


1. The app captures video from the webcam.
2. **MediaPipe** processes hand landmarks in real-time.
3. A pre-trained **machine learning model** predicts the ASL sign.
4. Feedback is provided on-screen and via **Text-to-Speech**.
5. Real-time progress updates are displayed in the UI.

---

### **About This Version:**
This is the **beta version (v1.0)** of the ASL recognition app, which is beyond the MVP phase. It accurately identifies hand signs and provides feedback, setting the foundation for future features like enhanced ASL learning modes, more advanced feedback, and better user interaction.

---

This project aims to make **learning American Sign Language** interactive, engaging, and accessible for everyone 
