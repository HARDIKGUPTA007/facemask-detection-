
# **Facemask Detection**

## **Overview**
Facemask Detection is an AI-powered project that utilizes deep learning and computer vision to identify whether individuals are wearing face masks correctly. The system can classify faces as **masked**, **unmasked**, or **improperly masked**, making it useful for enforcing health protocols in various environments.

---

## **Setup Instructions**

### **Clone the Repository**
Clone the Ultralytics YOLO repository for facemask detection:  
```bash
git clone https://github.com/ultralytics/ultralytics
cd ultralytics
```

### **Install Dependencies**
Install the required libraries for YOLOv8 and Roboflow:  
```bash
pip install ultralytics
pip install roboflow
```

### **Download the Dataset**
Use Roboflow to access the facemask dataset and prepare it for training:  
```python
from roboflow import Roboflow

rf = Roboflow(api_key="YOUR_API_KEY")
project = rf.workspace("YOUR_WORKSPACE_NAME").project("mask-wearing")
dataset = project.version(4).download("yolov8")
```

Replace `YOUR_API_KEY` and `YOUR_WORKSPACE_NAME` with your Roboflow API key and workspace name.

### **Train the Model**
Train the YOLOv8 model using the downloaded dataset:  
```python
from ultralytics import YOLO

model = YOLO("yolov8n.pt")  # Load pre-trained YOLOv8 model
model.train(data="dataset.yaml", epochs=50)  # Train on facemask dataset
```

### **Test the Model**
Run the trained model on test images or video:  
```python
results = model.predict(source="path/to/test/image_or_video.mp4", show=True)
```

---

## **Features**
1. **Real-Time Detection**: Detects facemask usage in live camera feeds or video footage.  
2. **Multi-Class Classification**: Identifies faces as masked, unmasked, or improperly masked.  
3. **High Accuracy**: Trained on diverse datasets for robust performance across conditions.  
4. **Custom Alerts**: Provides visual or audible notifications for non-compliance.

---

## **Technologies Used**
- **YOLOv8**: A state-of-the-art object detection model.  
- **Roboflow**: For dataset management and augmentation.  
- **Python Libraries**: OpenCV, TensorFlow, and PyTorch.

---

## **Applications**
1. **Public Health**: Enforces mask compliance in crowded areas.  
2. **Workplace Safety**: Monitors mask usage in offices and factories.  
3. **Education**: Ensures proper mask usage in schools.  
4. **Event Management**: Controls compliance in large gatherings.

---

## **Future Enhancements**
1. **Mask Type Identification**: Detect specific mask types like N95 or surgical masks.  
2. **Crowd Analytics**: Analyze trends in mask compliance.  
3. **IoT Integration**: Deploy on standalone hardware for real-time monitoring.

---

## **Acknowledgments**
- **Ultralytics**: For providing YOLOv8 as a robust object detection framework.  
- **Roboflow**: For accessible datasets and tools.  
- Open-source communities for their contributions to AI and computer vision.

---

## **License**
This project is licensed under the [MIT License](LICENSE).

---

## **Contact**
For inquiries or contributions, feel free to contact [your email/contact info].
