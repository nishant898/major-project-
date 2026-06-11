# 👁️ SightSync — Real-Time Generative UI for Accessibility

> **SightSync** is a real-time Chrome Extension that transforms any webpage into an accessible interface. It provides an on-page accessibility toolbar with custom filters and modes designed for users with visual, motor, or cognitive accessibility needs.

---

## ✨ Features

- 🛠️ **Accessibility Toolbar** — Injected on-page toolbar with 12 toggleable accessibility modes:
  - **High Contrast**: Maximum readability for low contrast sensitivity.
  - **Low Vision**: Adjustable larger text and elements.
  - **Color Blind**: Filter adjustments for color vision deficiency.
  - **Tunnel Vision**: Center-focused layout helper.
  - **Peripheral Vision**: Edge-focused layout helper.
  - **Blurry Vision**: Sharpened visual aids.
  - **Focus Mode**: Distraction-free reading by hiding ads/sidebars.
  - **Smart Highlight**: Interactive element highlighting for easy tab navigation.
  - **Large Cursor**: Enhanced pointer visibility.
  - **Voice Mode**: Text-to-speech engine reading hovered elements.
  - **Remove Images**: Cognitive focus aid by hiding all images.
  - **Magnifier**: Digital zoom lens tracking the cursor.
- 🌗 **Light/Dark Theme Toggle** — Personalize the accessibility toolbar's visual style.
- 🔐 **User Authentication** — Secure login/logout via Supabase (Google OAuth).
- ⭐ **User Feedback System** — Direct feedback form and overall rating summary powered by Supabase.

---

## 🗂️ Project Structure

```
ui extension/
├── extension/                  # Chrome Extension (Frontend & Core Logic)
│   ├── manifest.json           # Extension config (Manifest V3)
│   ├── supabase-js.js          # Supabase Client SDK
│   ├── popup/
│   │   ├── popup.html          # Extension popup UI
│   │   ├── popup.css           # Popup styles
│   │   ├── popup.js            # Popup controls & toggles
│   │   └── supabaseClient.js   # Supabase client initializer
│   ├── background/
│   │   └── background.js       # Service worker handling Auth and DB requests
│   └── content/
│       ├── content.js          # Injected accessibility toolbar script
│       └── content.css         # Injected custom accessibility styles
│
└── backend/                    # Python FastAPI Backend (Optional / Future Development)
    ├── main.py                 # FastAPI application template
    ├── requirements.txt        # Python dependencies
    └── services/
        └── openai_service.py   # OpenAI service utility template
```

---

## 🧩 Extension Setup (Chrome)

### 1. Configure Supabase (Prerequisites)
Since auth and ratings connect directly to Supabase from the extension background script, ensure you have:
- A Supabase Project set up.
- A `reviews` table matching the schema used in `background.js` (columns: `user_id`, `rating`, `feedback`).
- Setup your OAuth redirects in Supabase and Chrome Identity API.
- Configured connection details in [supabaseClient.js](file:///c:/Users/nisha/Desktop/ui%20extension/extension/popup/supabaseClient.js).

### 2. Open Chrome Extensions
Navigate to: `chrome://extensions/` in your Chrome browser.

### 3. Enable Developer Mode
Toggle **Developer mode** to ON (located in the top-right corner).

### 4. Load the Extension
Click the **"Load unpacked"** button and select the `extension/` directory from this project.

### 5. Pin & Use
- Pin **SightSync** in your Chrome toolbar.
- Click the icon and log in with Google.
- Toggle the **Toolbar** switch on to begin using accessibility modes on any webpage.

---

## ⚙️ Optional Backend Setup (Developer Reference)

If you wish to run the FastAPI development server:

### 1. Navigate to the backend folder
```bash
cd backend
```

### 2. Create and Activate Virtual Environment
```bash
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate
```

### 3. Install dependencies & Run
```bash
pip install -r requirements.txt
python main.py
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Chrome Extension | HTML, CSS, Vanilla JavaScript (MV3) |
| Backend (Optional) | FastAPI, Uvicorn |
| Database & Auth | Supabase |

---


---




