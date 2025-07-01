# 🧪 How to Test Smart S3 Image Uploader Locally

This guide helps you test the Smart S3 Image Uploader on your local system after cloning from GitHub.

---

## ✅ Step 1: Clone the Repository

```bash
git clone https://github.com/SuyashSrivastava45/Smart_S3_Image_Uploader.git
cd Smart_S3_Image_Uploader
```

---

## ✅ Step 2: Install Dependencies

Make sure Python is installed, then run:

```bash
pip install -r requirements.txt
```

---

## ✅ Step 3: Configure AWS

Make sure AWS CLI is installed and run:

```bash
aws configure
```

Enter:
- Your AWS Access Key
- Your Secret Access Key
- Region (e.g., `ap-south-1`)
- Output format (optional)

---

## ✅ Step 4: Edit Configuration in `main.py`

Open `main.py` and update the following:

```python
S3_BUCKET = 'your-s3-bucket-name'
SNS_TOPIC_ARN = 'your-sns-topic-arn'
```

Use the actual S3 bucket name and SNS topic ARN you created.

---

## ✅ Step 5: Run the Application

```bash
python main.py
```

---

## ✅ Test Cases to Try

| Scenario                        | Expected Outcome |
|----------------------------------|------------------|
| Upload from File                 | Preview shown, image uploaded to S3, email sent |
| Capture from Webcam              | Webcam opens, image captured and previewed |
| Wrong file format or cancel      | Error handled with friendly message |
| No AWS or wrong config           | Upload fails, error shown |
| No webcam or blocked             | Graceful error for webcam issue |

---

## 🛠️ Troubleshooting

- `Unable to access webcam`: Check camera permissions
- `Upload failed`: Confirm AWS credentials and bucket/ARN are correct
- `Module not found`: Reinstall with `pip install -r requirements.txt`

---

## ✅ Reminder

Do not use GitHub Actions to run this GUI application. It must be run locally on a desktop with Python, webcam, and internet access.

