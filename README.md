# DATA-PIPELINE-DEVELOPMENT

COMPANY: CODTECH IT SOLUTIONS  
NAME: ADITYA KANWAR  
INTERN ID: CT06DF952  
DOMAIN: DATA SCIENCE
DURATION: 6 WEEKS  
MENTOR: NEELA SANTOSH  

Objective:
The objective of Task is to build a complete and automated data pipeline that handles common data preprocessing steps — extraction, transformation, and loading — which are essential in any machine learning project. This pipeline was developed using Python, with the help of libraries like Pandas, NumPy, and Scikit-learn. The task involved cleaning raw data, handling missing values, encoding categorical variables, scaling numerical features, and organizing everything into a clean and reusable pipeline using Scikit-learn’s Pipeline and ColumnTransformer.

Project Overview:
In this task, I created a preprocessing pipeline using the Titanic dataset from Seaborn’s repository. The project utilizes `Pandas`, `Scikit-learn`, and `NumPy` to automate the data transformation process using reusable pipelines.

Tools & Libraries Used:

Python 3.9
- Pandas – Data ingestion and manipulation
- NumPy – Numerical computations
- Scikit-learn – Pipelines, transformers, and preprocessing
- Seaborn (indirectly via the Titanic dataset URL)


Dataset Used:
For this task, the Titanic dataset was used. It was directly fetched from the official Seaborn GitHub repository. This dataset contains passenger information (such as age, gender, class, fare, etc.) and the target column survived which indicates whether the passenger survived or not. This dataset is widely used for practice in data science and machine learning due to its variety of features and presence of both categorical and numerical data.

Workflow and Steps:
1. Data Loading and Inspection:
The dataset was loaded into a Pandas DataFrame from the URL using pd.read_csv(). Initial inspection using .head() was done to verify the structure and view sample rows. The dataset had a mix of numeric and categorical columns, some of which contained missing values.
2. Feature Separation:
The data was split into features (X) and the target (y). The target column survived was separated for model training purposes. Further, the features were categorized based on their data types into numerical and categorical features using select_dtypes().
3. Preprocessing Pipelines:
• Numeric Pipeline: A pipeline was constructed for numerical features which included:
• Imputation: Missing values were filled using the mean strategy with SimpleImputer.
• Scaling: Features were standardized using StandardScaler to bring them on the same scale.
• Categorical Pipeline: For categorical features:
• Imputation: Missing values were filled with the most frequent value.
• Encoding: Applied OneHotEncoder to convert categorical columns into binary columns (one-hot vectors), handling unknown categories safely.
4. ColumnTransformer and Integration:
Both the numerical and categorical pipelines were combined using Scikit-learn’s ColumnTransformer. This allows different preprocessing strategies to be applied to specific columns in a single step. The column transformer was then embedded into a higher-level Pipeline called etl_pipeline to automate the entire preprocessing process.
5. Train-Test Splitting and Execution:
The dataset was then split into training and testing sets using train_test_split(), with 50% of the data used for each. The preprocessing pipeline was fit on the training data using fit_transform() and then used to transform the test data. This separation ensures that the pipeline does not leak information from the test set during training.
6. Output Verification:
The shapes of the processed train and test data matrices were printed and verified. After encoding, the number of columns increased due to the categorical variables being converted into multiple binary columns. For instance:
Train shape: (445, 28) Test shape: (446, 28) 
This confirmed that all preprocessing steps were correctly applied and consistent across the training and testing datasets.

 Output Example:

Train shape: (445, 28)
Test shape: (446, 28)

The output shape indicates successful one-hot encoding and transformation applied to the dataset.

Folder Structure:

task_1_data_pipeline/
├── titanic_etl_pipeline.ipynb   # Jupyter Notebook with pipeline code
├── README.md                    # Task documentation

Key Highlights:

• The entire preprocessing task was modularized into pipelines, making it clean, reusable, and scalable.

• Real-world challenges like missing values and mixed data types were handled efficiently using appropriate strategies.

• The project followed good machine learning practices, like separating preprocessing and model training, and ensuring that transformations were only learned from training data.

• The usage of Scikit-learn’s Pipeline and ColumnTransformer showcases industry-standard methodology for preparing data for modeling.
