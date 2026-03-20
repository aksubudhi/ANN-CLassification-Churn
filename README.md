# Customer Churn Prediction with Artificial Neural Networks

## 📊 Project Overview

This project implements an Artificial Neural Network (ANN) model to predict customer churn for a bank. The model analyzes customer data to identify individuals likely to leave the bank, enabling proactive retention strategies. The project includes both the trained model and a user-friendly web application for real-time predictions.

## ✨ Features

- **Real-time Prediction Web App**: Interactive Streamlit application for instant churn predictions
- **Trained ANN Model**: TensorFlow-based neural network with ~86% accuracy
- **Complete Preprocessing Pipeline**: Automated data transformation and scaling
- **Interactive Dashboard**: User-friendly interface with sliders and dropdowns
- **Probability Outputs**: Provides both prediction and confidence scores

## 📈 Dataset Information

The model is trained on the **Churn_Modelling.csv** dataset containing:
- **10,000 customer records**
- **14 features** including demographics, account details, and banking behavior
- **Target variable**: Exited (1 = Churned, 0 = Retained)
- **Churn rate**: Approximately 20.4%

### Key Features:
- CreditScore, Age, Tenure, Balance, NumOfProducts
- HasCrCard, IsActiveMember, EstimatedSalary
- Geography (France, Spain, Germany)
- Gender (Male, Female)

## 🧠 Model Architecture

**Neural Network Configuration:**
- **Input Layer**: 12 features (after preprocessing)
- **Hidden Layer 1**: 64 neurons, ReLU activation
- **Hidden Layer 2**: 32 neurons, ReLU activation
- **Output Layer**: 1 neuron, Sigmoid activation
- **Optimizer**: Adam
- **Loss Function**: Binary Crossentropy
- **Metrics**: Accuracy

## 🚀 Installation & Setup

### Prerequisites
- Python 3.8+
- Virtual environment (recommended)

### Step-by-Step Installation

1. **Clone or download the project**
   ```bash
   cd /path/to/project
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv enb
   source enb/bin/activate  # On Windows: enb\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Verify installation**
   ```bash
   python -c "import streamlit, tensorflow, sklearn, pandas; print('All dependencies installed successfully')"
   ```

## 🎯 Usage

### Running the Web Application

1. **Start the Streamlit app**
   ```bash
   streamlit run app.py
   ```

2. **Access the application**
   - Open your browser to `http://localhost:8501`
   - Fill in customer details using the interactive form
   - Click predict to get churn probability

### Input Parameters

The application requires the following customer information:
- **Geography**: Customer's country (France, Spain, Germany)
- **Gender**: Male or Female
- **Age**: 18-92 years
- **Balance**: Account balance
- **Credit Score**: Credit score (350-850)
- **Estimated Salary**: Annual salary
- **Tenure**: Years with bank (0-10)
- **Number of Products**: 1-4 products
- **Credit Card**: Has credit card (Yes/No)
- **Active Member**: Is active member (Yes/No)

## 📊 Performance Metrics

- **Accuracy**: ~86%
- **Precision**: High for churn prediction
- **Recall**: Effective at identifying at-risk customers
- **AUC-ROC**: Strong discriminatory power

### Key Insights from Data Analysis:
- German customers show highest churn rate
- Females slightly more likely to churn than males
- Age 40-60 shows highest churn probability
- Inactive members are 2x more likely to churn
- Low credit score correlates with higher churn

## 📁 Project Structure

```
annclassification/
│
├── app.py                    # Streamlit web application
├── model.h5                  # Trained ANN model
├── Churn_Modelling.csv       # Training dataset
├── requirements.txt          # Python dependencies
├── experiments.ipynb         # Model development notebook
├── prediction.ipynb          # Prediction analysis notebook
├── README.md                 # Project documentation
│
├── enb/                      # Virtual environment
│   ├── bin/
│   ├── lib/
│   └── ...
│
├── logs/                     # TensorBoard logs
│   ├── fit20260317-172634/
│   └── fit20260317-182130/
│
└── Preprocessing files:
    ├── label_encoder_gender.pkl
    ├── one_hot_encoder.pkl
    └── scaler.pkl
```

## 🛠️ Tech Stack

### Core Technologies
- **Python 3.11**: Primary programming language
- **TensorFlow 2.x**: Deep learning framework for ANN model
- **Keras**: High-level neural networks API (integrated with TensorFlow)
- **Streamlit**: Web application framework for interactive UI

### Data Processing & Analysis
- **pandas**: Data manipulation and analysis
- **NumPy**: Numerical computing and array operations
- **scikit-learn**: Machine learning preprocessing and evaluation
  - StandardScaler for feature normalization
  - LabelEncoder for categorical encoding
  - OneHotEncoder for geography encoding

### Model Persistence & Serialization
- **Pickle**: Python object serialization for saving encoders and scalers
- **HDF5 (.h5)**: TensorFlow model storage format

### Development Environment
- **Jupyter Notebook**: Interactive development and experimentation
- **Virtual Environment (venv)**: Isolated Python environment
- **pip**: Package management and dependency installation

### Additional Libraries
- **matplotlib/seaborn**: Data visualization (used in notebooks)
- **TensorBoard**: Model training monitoring and visualization

## 💼 Business Value

### Cost-Benefit Analysis:
- **Retention Cost**: $50-200 per customer (offers, calls)
- **Acquisition Cost**: $300-600 per new customer
- **ROI**: 3-5x return on retention investments

### Strategic Benefits:
- **Proactive Retention**: Identify at-risk customers before they leave
- **Targeted Marketing**: Personalized retention campaigns
- **Resource Optimization**: Focus efforts on high-probability churn cases
- **Revenue Protection**: Reduce customer lifetime value loss

## 🔮 Future Improvements

### Model Enhancements:
- **Deep Learning**: Experiment with deeper architectures
- **Feature Engineering**: Create derived features
- **Ensemble Methods**: Combine multiple models
- **Regularization**: Add dropout and batch normalization

### Application Features:
- **Batch Predictions**: Process multiple customers simultaneously
- **Historical Analysis**: Track prediction trends over time
- **A/B Testing**: Compare retention strategies
- **API Integration**: REST API for system integration

### Data & Infrastructure:
- **Real-time Data**: Connect to live customer database
- **Model Retraining**: Automated model updates
- **Monitoring**: Track model performance in production
- **Scalability**: Deploy on cloud infrastructure

## ⚖️ Ethical Considerations

### Responsible AI Practices:
- **Privacy Protection**: No sensitive data storage in application
- **Bias Awareness**: Regular bias audits and mitigation
- **Transparency**: Clear explanation of model predictions
- **Fairness**: Equal treatment across demographic groups

### Data Ethics:
- **Consent**: Ensure proper data usage permissions
- **Anonymization**: Remove personally identifiable information
- **Security**: Secure handling of customer data
- **Accountability**: Clear responsibility for model decisions

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines:
- Follow PEP 8 style guidelines
- Add docstrings to functions
- Write unit tests for new features
- Update documentation


---

**Last Updated**: March 2026
**Model Version**: v1.0
**Python Version**: 3.11