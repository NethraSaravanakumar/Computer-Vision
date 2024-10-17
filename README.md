# Computer-Vision
Using computer vision to detect number plates in real-time and extract text with Tesseract OCR

1. Imports and Setup:

cv2 for handling computer vision tasks such as reading the video and detecting number plates.
PIL (Python Imaging Library) for image processing.
pytesseract for extracting text from images using Tesseract OCR.

2. Initial Configurations:

The camera frame dimensions are set to 640x480 (frameWidth, frameHeight), and the brightness is adjusted using cap.set(10, 150).
The cascade classifier is loaded for Russian number plates detection using haarcascade_russian_plate_number.xml.
Minimum area (minArea) is defined to filter out small detections.

3. Main Loop:

The video feed is read frame by frame using cap.read().
The frame is converted to grayscale (cv2.cvtColor) for easier processing.
The number plate detection is performed using detectMultiScale() to find potential plates.
For each detected number plate, a bounding box is drawn around the plate using cv2.rectangle(), and the region of interest (ROI) is displayed in a separate window (cv2.imshow("ROI", imgRoi)).

4. Capture and Save:

If the 's' key is pressed, the ROI containing the number plate is saved as an image (cv2.imwrite()).
A green rectangle with the text "Scan Saved" is shown on the image for visual feedback.

5. Text Extraction:

After saving the image, Tesseract OCR is used to extract text from the saved image of the number plate (tess.pytesseract.image_to_string()), and the extracted text is printed to the console.
Key Points:
Real-time video processing: Captures live video from the webcam and processes frames in real time.
Number plate detection: Uses Haar Cascade to detect number plates in each frame.
Text recognition: Uses Tesseract OCR to extract text from the detected number plates and prints it.
