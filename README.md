# AR-Virtual-Painter

## ✍️ Create Digital Art with Hand Gestures & Computer Vision

- This project transforms your webcam into a canvas, allowing you to draw and create digital art in real-time using simple hand gestures. The application uses MediaPipe for hand tracking to provide an intuitive, touch-free painting experience.

## 💡 Features

- **Real-Time Drawing**: Paint on your screen by moving your index finger.
- **Intuitive Controls**: Switch between drawing and selection modes using two-finger gestures.
- **Color Palette**: Select different colors (magenta, blue, green) from a dynamic on-screen menu.
- **Eraser Tool**: A simple gesture allows you to erase parts of your drawing.

## ⚡ How It Works

The core of the project relies on real-time hand landmark detection and image manipulation:

1. **Hand & Finger Tracking**  
   The code uses the `HandTrackingModule` to detect a hand in the video feed and track the positions of the fingertips.
2. **Mode Switching**
   - **Selection Mode**  
     When both the index and middle fingers are extended, the application enters selection mode. You can move your index finger over the color header to choose a drawing color or activate the eraser.
   - **Drawing Mode**  
     When only the index finger is extended, the application enters drawing mode. The program draws a line on a virtual "canvas" by connecting the current and previous positions of the index fingertip.
3. **Virtual Canvas**  
   A black `imgCanvas` is created to act as the drawing surface. The lines drawn by your finger are rendered onto this canvas.
4. **Image Blending**  
   The virtual canvas is then logically combined with the live webcam feed using bitwise operations (`cv2.bitwise_and` and `cv2.bitwise_or`). This process creates the effect of a transparent overlay, making it appear as though you are drawing directly on the live video.

## 💾 Requirements

To run this project, you need the following Python libraries:

- opencv-python
- numpy
- **HandTrackingModule**: A custom module containing the functions for hand tracking, landmark detection, and finger state recognition.
