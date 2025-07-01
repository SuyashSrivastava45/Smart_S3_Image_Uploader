# Smart S3 Image Uploader

## Overview

Smart S3 Image Uploader is a Python-based desktop application that enables users to upload images to an AWS S3 bucket either from their local disk or directly captured from a webcam. The application integrates AWS S3 for storage, AWS SNS for notifications, OpenCV for image processing, and Tkinter for the graphical user interface.

## Features

* **File Upload**: Select and upload image files (JPG, JPEG, PNG, BMP, GIF) from local disk to AWS S3.
* **Webcam Capture**: Capture images directly from a webcam and upload them to S3.
* **Image Preview**: Preview images using OpenCV before uploading.
* **AWS SNS Notifications**: Send email notifications via AWS SNS upon successful upload.
* **User-Friendly GUI**: Built with Tkinter, providing an intuitive interface with real-time status updates.

## Prerequisites

* **Python**: Version 3.12.7 or compatible.
* **AWS Account**: Configured with access to S3 and SNS services.
* **Dependencies**:

  * `boto3`: AWS SDK for Python.
  * `opencv-python`: For image capture and preview.
  * `tkinter`: For the GUI (usually included with Python).
* **Webcam**: Required for capturing images directly.
* **AWS Credentials**: Properly configured for boto3 (e.g., via AWS CLI or credentials file).

## Installation

1. **Clone the Repository** (if applicable):

   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Install Dependencies**:

   ```bash
   pip install boto3 opencv-python
   ```

3. **Configure AWS Credentials**:

   * Ensure AWS credentials are set up in `~/.aws/credentials` or via environment variables.
   * Example credentials file:

     ```ini
     [default]
     aws_access_key_id = YOUR_ACCESS_KEY
     aws_secret_access_key = YOUR_SECRET_KEY
     ```

4. **Set Up AWS Resources**:

   * Create an S3 bucket (e.g., `imageswithboto3`).
   * Create an SNS topic and note its ARN (e.g., `arn:aws:sns:ap-south-1:686255986807:s3upload`).
   * Subscribe an email address to the SNS topic for notifications.

## Configuration

Edit the following variables in the `finalproject.ipynb` notebook:

* `S3_BUCKET`: Set to your S3 bucket name (e.g., `imageswithboto3`).
* `SNS_TOPIC_ARN`: Set to your SNS topic ARN (e.g., `arn:aws:sns:ap-south-1:686255986807:s3upload`).

## Usage

1. **Run the Application**:

   * Open `finalproject.ipynb` in Jupyter Notebook.
   * Execute all cells to launch the Tkinter GUI.

2. **Interface Overview**:

   * **Upload from File**: Click to select an image from your local disk.
   * **Capture from Webcam**: Click to open the webcam feed, press `SPACE` to capture, or `ESC` to cancel.
   * **Status Bar**: Displays real-time status (e.g., "Ready", "Uploaded", or error messages).
   * **Preview Window**: Displays the selected or captured image before upload.

3. **Uploading Process**:

   * After selecting or capturing an image, a preview window opens.
   * Press any key to confirm the upload to S3.
   * Receive a confirmation message and SNS email notification upon successful upload.

## Code Structure

* **Module Imports**: Imports `boto3`, `cv2`, `os`, `uuid`, `threading`, and `tkinter` for core functionality.
* **AWS Configuration**: Initializes S3 and SNS clients with specified bucket and topic ARN.
* **GUI Setup**: Configures the Tkinter window with buttons, labels, and status updates.
* **Use Cases**:

  * **File Upload**: Uses `filedialog` to select images and upload them.
  * **Webcam Capture**: Uses OpenCV to capture images and save them locally before upload.
  * **Image Preview**: Displays images using OpenCV before uploading.
  * **S3 Upload & SNS Notification**: Uploads images to S3 and sends notifications via SNS.
* **GUI Widgets**: Defines buttons and labels for user interaction.

## Error Handling

* Validates file selection and webcam access.
* Handles image reading errors with OpenCV.
* Catches and displays AWS-related errors (e.g., upload failures).
* Uses `messagebox` for user-friendly error and success notifications.

## Limitations

* Requires a stable internet connection for AWS interactions.
* Webcam functionality depends on compatible hardware.
* SNS notifications require a valid subscription to the topic.
* No batch upload support for multiple images.

## Troubleshooting

* **"Unable to access webcam"**: Ensure the webcam is connected and not in use by another application.
* **"Upload failed"**: Verify AWS credentials, bucket name, and SNS topic ARN.
* **"Unable to read image"**: Check if the selected file is a valid image format.

## Future Enhancements

* Add support for batch image uploads.
* Implement image compression before upload.
* Add progress bars for upload status.
* Support additional file formats or video capture.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details (if applicable).

## Author

**Suyash Prakash Srivastava**
B.Tech Student | Python Developer | Cloud & ML Enthusiast
[LinkedIn](https://www.linkedin.com/in/suyash-prakash-srivastava-00897232a) • [GitHub](https://github.com/SuyashSrivastava45) • Email: [suyashsrivastava614@gmail.com](mailto:suyashsrivastava614@gmail.com)
