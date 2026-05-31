# SignBridge

An intelligent Indian Sign Language (ISL) translator application that bridges the communication gap between sign language users and the broader community.

## Project Overview

SignBridge is a comprehensive web-based platform that enables real-time translation between Indian Sign Language and text. The application features multiple modes including:

- **Sign to Text**: Convert sign language gestures to written text using computer vision
- **Text to Sign**: Get visual demonstrations of how to sign words and phrases
- **Learn Mode**: Educational interface for learning ISL
- **ISL Cards**: Flash card-style learning tool
- **ISL Translator**: Real-time translation interface

## Project Structure

### Frontend (`Cards/`)

React-based web application with Material-UI components. Handles user interface and real-time video processing.

```
Cards/
├── src/
│   ├── components/
│   │   ├── HomePage.js                 # Landing page
│   │   ├── ISLCardsPage.js             # Flash card learning interface
│   │   ├── ISLTranslator.js            # Main translation interface
│   │   ├── LearnPage.js                # Learning mode
│   │   ├── SignToTextPage.js           # Sign language to text conversion
│   │   ├── TextToSignPage.js           # Text to sign demonstration
│   │   ├── SignButton.js               # Reusable sign button component
│   │   └── ControlButtons.js           # Control interface buttons
│   ├── App.js                          # Main application component
│   ├── index.js                        # React entry point
│   └── App.css                         # Global styles
├── public/
│   ├── index.html                      # HTML template
│   └── isl_words_data.json             # ISL vocabulary data
│   └── train1/                         # Training images organized by letter (0-9, A-Z)
├── backend/
│   ├── server.js                       # Node.js server for frontend
│   └── package.json
└── package.json
```

### Backend (`StoT/`)

Python-based machine learning backend for sign language processing and recognition.

```
StoT/
└── backend/
    ├── app.py                          # Flask API server
    ├── ttos.py                         # Text-to-sign conversion logic
    ├── python/
    │   └── sign_language.py            # Core sign language processing
    ├── models/
    │   ├── skeletal_class_indices.json # Model class mappings
    │   ├── skeletal_class_indices2.json
    │   └── class_indices.json
    └── assets/
        └── isl_videos_map.json         # Video mapping data
```

## Technology Stack

### Frontend
- **React** 18.2.0 - UI framework
- **Material-UI (MUI)** 5.13.0 - Component library
- **React Router** 7.6.2 - Navigation
- **React Webcam** 7.2.0 - Camera access
- **Axios** 1.4.0 - HTTP client

### Backend
- **Flask** - Web framework
- **Flask-CORS** - Cross-origin resource sharing
- **OpenCV (cv2)** - Computer vision
- **Keras** - Deep learning models
- **CVZone** - Hand tracking module
- **PyTTSx3** - Text-to-speech
- **SpellChecker** - Spell checking for word completion

## Setup Instructions

### Prerequisites
- Node.js and npm (for frontend)
- Python 3.8+ (for backend)
- Webcam (for sign language recognition)

### Frontend Setup

1. Navigate to the Cards directory:
   ```bash
   cd Cards
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm start
   ```

The application will open at `http://localhost:3000`

### Backend Setup

1. Navigate to the StoT/backend directory:
   ```bash
   cd StoT/backend
   ```

2. Create a Python virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install Python dependencies:
   ```bash
   pip install flask flask-cors opencv-python keras numpy cvzone pyttsx3 pyspellchecker
   ```

4. Run the Flask server:
   ```bash
   python app.py
   ```

The backend API will be available at `http://localhost:5000`

## Features

### 1. Sign to Text
- Real-time video input from webcam
- Hand gesture recognition using trained ML models
- Converts detected signs to text
- Spell-checking for accuracy

### 2. Text to Sign
- Input text or words
- Display corresponding sign videos or static images
- Educational demonstrations

### 3. Learning Mode
- Interactive lessons for ISL
- Flash cards with sign demonstrations
- Progress tracking

### 4. ISL Translator
- Comprehensive translation interface
- Real-time processing
- Multi-language support ready

## Model Architecture

The application uses trained Keras models for sign recognition:
- Skeletal models (pose-based recognition)
- Class indices mapping for ISL signs
- Support for both static signs and dynamic gestures

## Vocabulary

- Training data organized alphabetically (0-9, A-Z)
- ISL words data in `isl_words_data.json`
- Video mapping in `isl_videos_map.json`

## API Endpoints

The Flask backend provides endpoints for:
- Sign recognition from video frames
- Text-to-sign conversion
- Vocabulary lookup
- Audio generation for text

## Contributing

Contributions are welcome! Areas for improvement:
- Expand ISL vocabulary database
- Improve model accuracy with more training data
- Add support for sentence-level translation
- Optimize performance
- Add mobile app support

## Future Enhancements

- [ ] Real-time continuous sign stream recognition
- [ ] Support for regional sign language variations
- [ ] Offline functionality
- [ ] Mobile application
- [ ] Integration with voice assistants
- [ ] Community contribution platform for new signs

## License

This project is open-source and available under MIT License.

## Support

For issues, feature requests, or questions, please open an issue in the repository.

---

**SignBridge** - Bridging Communication Through Sign Language
