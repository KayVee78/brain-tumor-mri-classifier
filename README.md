# 🧠 Brain Tumor MRI Classifier (Deep Learning)

This project is developed as the individual coursework for the **Applied AI** module (Year 4 – Semester 1), and aims to build an automated brain tumor classification system that supports radiologists by analysing MRI scans. The application uses a Convolutional Neural Network (CNN) to classify brain MRIs into four diagnostic categories **glioma**, **meningioma**, **pituitary tumor**, and **no tumor** and is intended as a clinical decision-support / triage aid rather than a standalone diagnostic tool.

The notebook also contains a written review of the problem domain and a comparative evaluation of three AI techniques (SVM, CNN, K-Means clustering) before settling on CNNs for the implementation.

---

## 🗝️ Key Features

- **Multi-Class MRI Classification**: Classifies brain MRI scans into four categories (glioma, meningioma, pituitary, no tumor) using a custom CNN built with TensorFlow / Keras.
- **Automated Data Pipeline**: Pulls the Kaggle *Brain Tumor MRI Dataset* on demand, with a guard that skips re-downloading if the data already exists locally.
- **Data Augmentation**: Applies on-the-fly rotation, width/height shifts, and horizontal flipping during training to improve generalisation on a relatively small medical dataset.
- **Exploratory Data Analysis**: Generates per-class image samples, a 3×3 grid of augmented training samples, and a class-distribution table across the train / validation / test splits.
- **CNN Training with Callbacks**: Trains using `EarlyStopping`, `ModelCheckpoint`, and `ReduceLROnPlateau` to prevent overfitting and recover the best-performing weights.
- **Comprehensive Evaluation**: Reports test accuracy, a full per-class classification report (precision / recall / F1), and a confusion matrix to surface which tumor types are most often confused.
- **Reproducible Results**: A fixed random seed is used across the data generators so runs are repeatable.

---

## ♦️ Prerequisites

This notebook is built to run on **Google Colab** with GPU acceleration enabled (`Runtime → Change runtime type → GPU`).

You will also need a free **Kaggle account** and an API token to download the dataset:

1. Go to [kaggle.com/settings](https://www.kaggle.com/settings) → *API* → **Create New Token**.
2. In Colab, open the **Secrets** panel (🔑 icon in the left sidebar) and add:
   - `KAGGLE_USERNAME` → your Kaggle username
   - `KAGGLE_KEY` → the key from your `kaggle.json`
3. Toggle **Notebook access** on for both secrets.

The notebook reads these via `google.colab.userdata`, so **no credentials are stored in the file**.

---

## 🚀 Running the Notebook

1. Open `.ipynb` file in Google Colab.
2. Configure your Kaggle secrets as described above.
3. Mount your Google Drive when prompted (used for saving model checkpoints).
4. Run all cells, the dataset will download automatically on first run.

---

## 🛠 Technologies Used

   ![Python]   &nbsp; Primary language for the entire pipeline — data loading, model building, training, and evaluation.
   <br/><br/>
   ![TensorFlow]   &nbsp; Deep learning framework used to build, train, and serialise the CNN.
   <br/><br/>
   ![Keras]   &nbsp; High-level API on top of TensorFlow for defining the layered CNN architecture and training callbacks.
   <br/><br/>
   ![scikit-learn]   &nbsp; Used for the classification report, confusion matrix, and accuracy metrics.
   <br/><br/>
   ![NumPy]   &nbsp; Numerical operations on image arrays and label vectors.
   <br/><br/>
   ![Pandas]   &nbsp; Tabular summaries of the dataset class distribution.
   <br/><br/>
   ![Matplotlib]   &nbsp; Plotting EDA samples, augmented grids, training curves, and the confusion matrix.
   <br/><br/>
   ![Colab]   &nbsp; Hosted runtime providing GPU acceleration and secret management for the Kaggle API.

---

## 📊 Dataset

This project uses the [Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset) by Masoud Nickparvar, distributed via Kaggle. It contains MRI scans labelled across four classes (glioma, meningioma, pituitary, no tumor), pre-split into `Training/` and `Testing/` folders. A 20% slice of the training set is held out as validation during training.

---

## ⚠️ Disclaimer

This is an academic coursework project. The model is **not** a certified medical device and must not be used for actual clinical diagnosis. Its purpose is to demonstrate applied AI techniques in a healthcare context.

---

## 👩‍💻 Author

**Kithmi Hettiarachchi (KayVee78)**
[GitHub Profile](https://github.com/KayVee78)

---

Happy coding! ☕

<!-- MARKDOWN LINKS & IMAGES -->
[Python]: https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white
[TensorFlow]: https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white
[Keras]: https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white
[scikit-learn]: https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white
[NumPy]: https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white
[Pandas]: https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white
[Matplotlib]: https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white
[Colab]: https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white
