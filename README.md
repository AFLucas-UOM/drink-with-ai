# Drink w/AI

`Drink w/AI` is a lightweight browser-based demo built for GDG-Malta. It uses a Google Teachable Machine image model with the user’s webcam to classify wine labels or bottles in real time.

## Features

- Real-time webcam classification with Google Teachable Machine
- First-load prompt for a Teachable Machine model code
- Model code persistence in `localStorage`
- Change/remove model code from the page UI
- Start and stop live camera feed controls
- Minimal branded footer with GDG-Malta links

## Project Structure

- `code.html` - Main single-page application
- `wine.png` - Favicon / branding asset

## Requirements

- A modern web browser
- A local web server
- Webcam access enabled in the browser
- A published Google Teachable Machine image model

## Run Locally

Serve the folder with any static web server, then open `code.html` in the browser.

Example with VS Code Live Server:

```text
Right-click code.html -> Open with Live Server
```

Example with Python:

```bash
python3 -m http.server 5500
```

Then open:

```text
http://127.0.0.1:5500/code.html
```

## Using a Model

On first load, the page asks for a Google Teachable Machine model code.
This code is used to build the model URL:

```text
https://teachablemachine.withgoogle.com/models/<MODEL_CODE>/
```

The app then loads:

- `model.json`
- `metadata.json`

The model code is stored in browser `localStorage` under:

```text
teachable-machine-model-code
```

## How It Works

1. The user enters a Teachable Machine model code.
2. The code is saved locally in the browser.
3. The app loads the model from Google Teachable Machine.
4. Webcam frames are sent to the model for prediction.
5. The UI updates the detected class label and confidence bars in real time.

## Credits

GDG-Malta  
Developed by [Andrea Filiberto Lucas](mailto:contact@aflucas.com) for the Drink w/AI Event.