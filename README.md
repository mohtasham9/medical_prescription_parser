# Medical Prescription Parsing Application

This repository contains a demo application designed to parse and extract information from handwritten medical prescriptions. The application leverages the GPT-4o model from OpenAI to accurately transcribe prescription details into structured data.

**Dataset**: [Kaggle Dataset](https://www.kaggle.com/datasets/mehaksingal/illegible-medical-prescription-images-dataset)
 
## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Prerequisites](#prerequisites)
4. [Setup Instructions](#setup-instructions)
5. [Running the Application](#running-the-application)
6. [Code Explanation](#code-explanation)
7. [Use Case](#use-case)
8. [Benefits](#benefits)
9. [Potential Issues](#potential-issues)
10. [Conclusion](#conclusion)

## Introduction

This project aims to streamline the process of reading and organizing handwritten medical prescriptions. By using the GPT-4o model, the application can decipher difficult handwriting and convert the information into a structured format, including patient details, doctor information, medications, and additional notes.

## Features

- Accurately transcribes handwritten medical prescriptions.
- Extracts and organizes patient and doctor information.
- Lists medications with dosage, frequency, and duration.
- Provides additional notes and instructions in a readable format.
- User-friendly web interface built with Streamlit.

## Prerequisites

Before setting up and running the application, ensure you have the following installed:

- Python 3.8 or higher
- OpenAI API Key
- Necessary Python libraries (listed in `requirements.txt`)

## Setup Instructions

Follow these steps to set up the development environment and run the application:

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/mohtasham9/medical_prescription_parser.git
    cd medical_prescription_parser
    ```

2. **Create a Virtual Environment**:
    ```bash
    python -m venv venv
    source venv/bin/activate    # On Windows, use `venv\Scripts\activate`
    ```

3. **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Set Up Environment Variables**:
    Create a `keys.py` file in the root directory and add your OpenAI API key:
    ```env
    OPENAI_API_KEY=your_openai_api_key
    ```

5. **Add Stylesheet**:
    Ensure you have a `styles.css` file in the root directory with your custom styles for the Streamlit app.

## Running the Application

To run the application, use the following command:
```bash
streamlit run app.py
```

Open your web browser and go to `http://localhost:8501` to access the application. You can upload prescription images and see the extracted information displayed on the web interface.

## Code Explanation

### Imports and Environment Setup

- Import necessary libraries and set environment variables.
- Use `os.environ` to securely manage the OpenAI API key.

### Load CSS for Streamlit

- Define a function to load and apply custom CSS styles from a `styles.css` file.

### Define Data Models

- Use Pydantic models (`MedicationItem` and `PrescriptionInformations`) to structure and validate extracted data.

### Load and Encode Images

- Define `load_images` function to read and encode images as base64.
- Set up `TransformChain` to handle image path transformations.

### Process and Extract Information

- Define `image_model` function to interact with GPT-4o for extracting prescription details.
- Use a detailed prompt to guide the AI in transcribing information accurately.
- Combine chains and parsers in `get_prescription_informations` function to process images and return structured data.

### Streamlit App Logic

- Initialize session state and set up file uploader for prescription images.
- Process uploaded images, display results in a formatted table, and clean up temporary files.

## Use Case

This application is particularly useful in healthcare settings where managing handwritten prescriptions can be challenging. It automates the transcription process, ensuring greater accuracy and efficiency, and can be integrated into existing healthcare systems for better workflow management.

## Benefits

- **Accuracy**: Reduces errors in transcription.
- **Efficiency**: Saves time for healthcare providers.
- **Integration**: Easily integrates with existing systems for a seamless workflow.

## Potential Issues

- **Image Quality**: Poor quality images may affect accuracy.
- **Handwriting Variability**: Highly illegible handwriting can be challenging for the AI.
- **API Limits**: Ensure you have sufficient quota for OpenAI API calls.

## Conclusion

This demo application demonstrates the potential of GPT-4o in revolutionizing healthcare practices by automating the transcription of handwritten prescriptions. With a straightforward setup and significant benefits, it is a valuable tool for improving accuracy and efficiency in healthcare management.



