# **Online Live Face Mask Detector**

This project implements a **real-time face mask detection system** using deep learning. It processes live video streams to detect faces and determine whether a person is wearing a mask or not. The system integrates with **Firebase** for real-time data logging and can be used in scenarios such as monitoring compliance with mask mandates in public spaces.

---

## **How It Works**

### **1. Real-Time Video Stream**
The system processes a live video feed from a connected camera:
- Each frame of the video is captured and passed to the detection pipeline.
- Multiple faces in a single frame can be detected and classified simultaneously.

---

### **2. Face Detection**
The first step involves detecting faces in the input frames:
- A **pre-trained face detection model** (e.g., MobileNet or SSD) identifies bounding boxes around faces.
- Detected regions are cropped and passed to the mask classification model.

---

### **3. Mask Classification**
The system uses a **deep learning classification model** to determine whether a detected face is wearing a mask:
- The cropped face image is resized and preprocessed.
- The model predicts one of two classes:
  - **Mask**: The person is wearing a mask.
  - **No Mask**: The person is not wearing a mask.
- The output also includes a confidence score for the prediction.

---

### **4. Real-Time Annotations**
The system overlays annotations on the video feed:
- Bounding boxes around detected faces.
- Labels such as "Mask" or "No Mask" with confidence scores.
- Different colors are used for mask compliance (e.g., green for "Mask," red for "No Mask").

---

### **5. Firebase Integration**
The system integrates with **Firebase** for real-time data storage:
- Detection results, including timestamps, class labels, and confidence scores, are logged to Firebase.
- This enables centralized monitoring and data analytics.

---

## **Key Outputs**
- **Live Annotated Video Feed**:
  - The video stream shows real-time detections with bounding boxes and labels.
- **Firebase Logs**:
  - Detection data is uploaded to Firebase for further analysis or reporting.

---

## **Example Workflow**
1. **Input**:
   - A live video feed from a camera.
2. **Processing**:
   - Faces are detected, and each face is classified as "Mask" or "No Mask."
3. **Output**:
   - Annotated video feed with bounding boxes and labels.
   - Real-time logging to Firebase.

---

## **Applications**
- **Public Safety**: Monitor mask compliance in public areas like malls, airports, and offices.
- **Event Management**: Ensure attendees follow mask mandates at large gatherings.
- **Healthcare Facilities**: Enhance safety in hospitals and clinics by monitoring staff and visitors.

---

### **Example Use Case**
- **Input Video**:  
   A live feed from a security camera in a public space.
- **Detection**:  
   Faces are identified, and each is classified for mask compliance.
- **Output Video**:  
   The feed displays bounding boxes with "Mask" (green) or "No Mask" (red) labels, and logs the results in Firebase.
