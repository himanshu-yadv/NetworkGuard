# NetworkGuard

A machine learning project for network security to predict whether a network connection is malicious or benign.

## Table of Contents

- [About the Project](#about-the-project)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)

---

## About the Project

This project aims to build and deploy a machine learning model that can classify network traffic as either malicious or benign. It uses a FastAPI backend to serve the model and provides an endpoint for making predictions on new data. The project is structured as a complete machine learning pipeline, from data ingestion to model training and deployment.

---

## Getting Started

### Prerequisites

- Python 3.8 or higher
- MongoDB account
- Git

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/himanshu-yadv/networkguard.git](https://github.com/himanshu-yadv/networkguard.git)
    cd networkguard
    ```

2.  **Create a virtual environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Set up environment variables:**
    Create a `.env` file in the root directory and add your MongoDB connection string:
    ```
    MONGO_DB_URL="your_mongodb_connection_string"
    ```

---

## Usage

1.  **Run the FastAPI server:**
    ```bash
    uvicorn app:app --host 0.0.0.0 --port 8080
    ```

2.  **Train the model:**
    To initiate the training pipeline, send a GET request to the `/train` endpoint. You can do this by navigating to `http://localhost:8080/train` in your browser or using curl:
    ```bash
    curl http://localhost:8080/train
    ```

3.  **Make predictions:**
    To get predictions, send a POST request to the `/predict` endpoint with a CSV file containing the network data. You can interact with this endpoint via the auto-generated FastAPI documentation at `http://localhost:8080/docs`.

    **Example using curl:**
    ```bash
    curl -X POST -F "file=@/path/to/your/data.csv" http://localhost:8080/predict
    ```
    The response will be an HTML table with the prediction results.

---

## Project Structure
