# 🦷 Tooth Detection using YOLOv10

	This project uses **YOLOv10** for detecting teeth and cavities in dental X-ray images.  
	The model is trained on a custom dataset annotated in YOLO format.


1. Clone The Reopsitory
	git clone https://github.com/pathakadithi/tooth-detection-yolov10.git
	cd tooth-detection-yolov10

2. Install Dependencies
	pip install -r requirements.txt

3.  Dataset

The dataset consists of dental X-ray images with bounding boxes for:

tooth

cavity

📥 Download Dataset & Weights (best.pt):
	 Google Drive Link : https://drive.google.com/file/d/11W8ESNM3UPP4BcQdLYfLO_o02NBZfMz5/view?usp=drive_link
	
	### 🚀 How to Use the Dataset in Google Colab

	```python
	# Mount Google Drive
	from google.colab import drive
	drive.mount('/content/drive')

	# Go to your dataset location (change path if needed)
	%cd /content/drive/MyDrive/

	# Unzip dataset
	!unzip -q "ToothNumber_TaskDataset.zip" -d /content/dataset/

	# Check dataset structure
	!ls /content/dataset/
	
	tooth_dataset.yaml:
	train: /content/dataset/images/train
	val: /content/dataset/images/val

	nc: 2
	names: ['tooth', 'cavity']

4.Training
	yolo detect train data=tooth_dataset.yaml model=yolov10s.pt epochs=60 imgsz=640

5.Inference(Run predictions on new images)
	yolo detect predict model=best.pt source="path/to/test/images"

6.📈 Results

Training & evaluation results are saved in sample_results/.

Example plots:

📊 Confusion Matrix

📉 Dataset Labels Distribution

📈 Training Loss & Accuracy Curves

7.## 🖼 Example Predictions

Here are some sample predictions from the model:

<p align="center">
  <img src="sample_results/example1.jpg" alt="Prediction 1" width="45%"/>
  <img src="sample_results/example2.jpg" alt="Prediction 2" width="45%"/>
</p>

8. ## Notebooks

The training code is provided in the [`ToothNumbengDetection.ipynb`](ToothNumbengDetection.ipynb) file.  
You can open it directly in [Google Colab](https://colab.research.google.com/) by uploading the notebook.





