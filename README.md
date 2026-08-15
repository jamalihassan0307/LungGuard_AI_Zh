# LungGuard AI

<div align="center">
  <img src="report%20data/ss/home.png" alt="LungGuard dashboard" width="1000" />
  <h3>AI-powered lung cancer detection for clinical decision support</h3>
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Django-4.2.10-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django" />
  <img src="https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/PyTorch-2.0.1-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" alt="PyTorch" />
  <img src="https://img.shields.io/badge/Model-ResNet18-5C2D91?style=for-the-badge&logo=tensorflow&logoColor=white" alt="ResNet18" />
</p>

LungGuard is a secure web application built with Django for AI-assisted lung cancer screening from chest X-ray images. It uses a trained ResNet18 deep learning model to classify scans into Normal, Benign, or Malignant categories and presents the result with a confidence score to support radiologist review.

## Overview

This project is designed for clinical environments where fast and reliable image analysis can help medical professionals detect early signs of lung cancer. Users can upload chest X-ray images, preprocess them, run inference with the trained model, and review predictions through a streamlined dashboard.

The platform includes:

- Secure authentication and user account management
- Chest X-ray upload and validation
- AI prediction using a trained ResNet18 model
- Classification into Normal, Benign, and Malignant
- Result history with searchable case tracking
- Dashboard analytics for prediction summaries
- Clinical workflow support with radiologist-friendly reporting

## Key Features

- Deep learning-based lung cancer detection from X-ray images
- Real-time classification with confidence scoring
- User-specific prediction history and case tracking
- Dashboard with summary statistics and recent analyses
- Medical interface for upload, result, and profile flows
- Model file integration from the local project repository
- Built with Django and PyTorch for scalable web deployment

## Model and Dataset

The project uses a ResNet18 model trained on the IQ-OTH/NCCD lung cancer dataset.

- Model file: `models/resnet18.pth`
- Output classes: Normal, Benign, Malignant
- Architecture: ResNet18 (CNN)
- Framework: PyTorch

This model is intended for decision support and should always be reviewed by a medical professional before final diagnosis.

## System Architecture

```mermaid
flowchart LR
    U[User / Radiologist] --> UI[Django Web Interface]
    UI --> AUTH[Authentication & Session Management]
    UI --> UPLOAD[Image Upload & Validation]
    UPLOAD --> PREP[Image Preprocessing]
    PREP --> MODEL[ResNet18 Inference Model]
    MODEL --> PRED[Normal / Benign / Malignant Prediction]
    PRED --> SAVE[(SQLite Database)]
    SAVE --> HIST[History, Results, Recent Cases]
    HIST --> DASH[Dashboard Analytics]
    DASH --> REPORT[AI Diagnostic Report]
```

## Tech Stack

- Python
- Django 4.2
- PyTorch
- TorchVision
- OpenCV
- Pillow
- NumPy
- SQLite
- HTML, CSS, JavaScript

## Screenshots

### Dashboard and Core Views

<div align="center">
  <table>
    <tr>
      <td align="center">
        <img src="report%20data/ss/dashboard.png" width="280" alt="Dashboard" /><br />
        <b>Dashboard</b>
      </td>
      <td align="center">
        <img src="report%20data/ss/home.png" width="280" alt="Home" /><br />
        <b>Home</b>
      </td>
      <td align="center">
        <img src="report%20data/ss/home1.png" width="280" alt="Home view" /><br />
        <b>Landing View</b>
      </td>
    </tr>
  </table>
</div>

### Authentication and User Management

<div align="center">
  <table>
    <tr>
      <td align="center">
        <img src="report%20data/ss/login.png" width="260" alt="Login" /><br />
        <b>Login</b>
      </td>
      <td align="center">
        <img src="report%20data/ss/create_account.png" width="260" alt="Create account" /><br />
        <b>Create Account</b>
      </td>
      <td align="center">
        <img src="report%20data/ss/change_password.png" width="260" alt="Change password" /><br />
        <b>Change Password</b>
      </td>
    </tr>
  </table>
</div>

### Analysis Workflow

<div align="center">
  <table>
    <tr>
      <td align="center">
        <img src="report%20data/ss/new_prediction.png" width="260" alt="New prediction" /><br />
        <b>New Analysis</b>
      </td>
      <td align="center">
        <img src="report%20data/ss/predicted_result.png" width="260" alt="Prediction result" /><br />
        <b>Prediction Result</b>
      </td>
      <td align="center">
        <img src="report%20data/ss/predicted_result1.png" width="260" alt="Detailed result" /><br />
        <b>Detailed Result</b>
      </td>
    </tr>
  </table>
</div>

### History, Profile, and Model Details

<div align="center">
  <table>
    <tr>
      <td align="center">
        <img src="report%20data/ss/history_page.png" width="260" alt="History" /><br />
        <b>History</b>
      </td>
      <td align="center">
        <img src="report%20data/ss/profile.png" width="260" alt="Profile" /><br />
        <b>Profile</b>
      </td>
      <td align="center">
        <img src="report%20data/ss/model_detail.png" width="260" alt="Model details" /><br />
        <b>Model Details</b>
      </td>
    </tr>
    <tr>
      <td align="center">
        <img src="report%20data/ss/model_detail2.png" width="260" alt="Model detail 2" /><br />
        <b>Model Overview</b>
      </td>
      <td align="center">
        <img src="report%20data/ss/recent_caese.png" width="260" alt="Recent cases" /><br />
        <b>Recent Cases</b>
      </td>
      <td align="center">
        <img src="report%20data/ss/about.png" width="260" alt="About page" /><br />
        <b>About</b>
      </td>
    </tr>
  </table>
</div>

## Project Workflow

1. User signs in or creates an account.
2. A chest X-ray image is uploaded through the dashboard.
3. The system validates and preprocesses the image.
4. The model predicts one of three classes: Normal, Benign, or Malignant.
5. Prediction details and confidence scores are saved to the database.
6. The result is displayed and stored in the history for later review.

## Installation and Setup

### 1) Clone the project

```bash
git clone <repository-url>
cd LUNGGUARD_AI
```

### 2) Create a virtual environment

```bash
python -m venv .venv
```

On Windows:

```powershell
.\.venv\Scripts\Activate.ps1
```

On macOS/Linux:

```bash
source .venv/bin/activate
```

### 3) Install dependencies

```bash
pip install -r requirements.txt
```

### 4) Apply database migrations

```bash
python manage.py migrate
```

### 5) Start the application

```bash
python manage.py runserver
```

Open the app in your browser:

```text
http://127.0.0.1:8000/
```

## Project Structure

```text
LUNGGUARD_AI/
├── detector/
│   ├── admin.py
│   ├── api_urls.py
│   ├── api_views.py
│   ├── auth_views.py
│   ├── config.py
│   ├── model_utils.py
│   ├── models.py
│   ├── preprocess.py
│   ├── serializers.py
│   ├── urls.py
│   └── views.py
├── lungguard/
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   └── asgi.py
├── models/
│   └── resnet18.pth
├── static/
├── templates/
├── uploads/
├── db.sqlite3
├── manage.py
├── requirements.txt
├── README.md
└── report data/
```

## References

1. IQ-OTH/NCCD Lung Cancer Dataset: https://www.kaggle.com/datasets/adityamahimkar/iqothnccd-lung-cancer-dataset
2. Django Documentation: https://docs.djangoproject.com/
3. PyTorch Documentation: https://pytorch.org/docs/
4. TensorFlow/PyTorch Documentation
5. World Health Organization - Cancer Fact Sheets
6. OWASP Web Security Guidelines
7. UML 2.5 Specification, Object Management Group (OMG)

## Conclusion

LungGuard demonstrates how modern deep learning and web technologies can be combined to support early lung cancer detection in a safe, user-friendly, and clinically meaningful workflow. It offers a strong foundation for medical imaging research, clinical decision support, and future expansion into broader diagnostic systems.

> This system is intended to assist medical professionals and should not replace professional clinical judgment.
