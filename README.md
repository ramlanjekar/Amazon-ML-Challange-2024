# Amazon ML Challange 2024

## Project Description

This project focuses on extracting structured data from product images, such as numerical values and their associated units (e.g., "50 kg"), which are often inconsistently represented in product descriptions. By combining the power of Optical Character Recognition (OCR), text preprocessing, and deep learning, this system aims to bridge the gap between raw textual data and meaningful, standardized information.

The pipeline involves robust text extraction using PaddleOCR, advanced text cleaning, and fine-tuned GPT-2 for extracting and formatting key details. It is designed to handle large datasets with efficiency and accuracy, making it ideal for applications in e-commerce, inventory management, and automated product cataloging.

---

## Key Features

1. **Comprehensive OCR Testing**:
   - Multiple OCR frameworks were evaluated for their accuracy and scalability.
   - **PaddleOCR** emerged as the best performer, especially for large datasets, due to its high accuracy in text recognition and GPU support.

2. **Sophisticated Text Cleaning**:
   - A multi-step pipeline processes OCR-extracted text to:
     - Standardize units (e.g., "kg" → "kilogram").
     - Separate numbers and units, ensuring consistency in representation.
     - Remove unwanted characters while preserving meaningful data.

3. **Deep Learning for Prediction**:
   - **Initial Approach**: A combination of SBERT-based text embeddings and product code embeddings passed through an MLP for predicting units and values. This method failed due to its complexity and difficulty in training effectively on diverse text data.
   - **Final Approach**: GPT-2 was fine-tuned on cleaned text data, enabling it to accurately extract and format product details, outperforming the initial method in both accuracy and simplicity.

4. **Scalability**:
   - Designed to process datasets with over 200,000 images using parallelized libraries such as Dask and Swifter, ensuring high-speed performance without compromising accuracy.

---

## Benefits

- **Accurate Data Extraction**: Handles complex and inconsistent text formats with ease.
- **Streamlined Processing**: Efficiently handles large-scale datasets using GPU-optimized libraries.
- **Customizability**: The fine-tuned GPT-2 model adapts to specific datasets and domain requirements.

---

### Prerequisites
Ensure the following dependencies are installed:

- Python 3.8 or higher
- GPU with CUDA support (recommended for PaddleOCR and GPT-2)
