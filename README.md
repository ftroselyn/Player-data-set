# Player-data-set
# Muskets Football Team: Player Data Cleaning, Preprocessing, and Prediction

# Introduction

The Muskets Football team is gearing up for the upcoming games season and sought assistance in preparing their player data for analysis. This project involves data cleaning, preprocessing, and building a predictive model to forecast the number of hits by each player.

In this README, we provide an in-depth account of the steps undertaken and the rationale behind each step.

# Data Source

The player dataset was downloaded from Kaggle, serving as the foundation for our analysis.

# Step 1: Data Preprocessing

. Player Names Extraction: We extracted player names from the PlayerUrl column, creating a new Player Name column for clear identification.

. Player Status Classification: A new Player Status column was generated from the CONTRACT column, with labels:

'Active': Players with active contracts.
'Free': Players who are free agents.
'On Loan': Players currently on loan.

. Positions Unpacking: The POSITIONS column was unpacked into separate columns for each position, with Boolean values assigned based on player positions.

. Data Type Conversion: Selected columns were converted to appropriate data types:

   Weight, Height, W/F, SM, and IR columns were converted to integers.
   Value, Wage, and Release Clause columns were converted to float.
   HITS Column Validation: The HITS column was inspected to ensure it held float data type.

. Categorical Clustering: New categorical columns were created for Height, Weight, Release Clause, Value, and Wage, with values converted into clusters/labels:

    Height was bucketed into intervals of 10 years.
    Weight was bucketed into intervals of 10 kg.
# Step 2: Data Cleaning

. Data Collection: The player dataset was sourced from Kaggle, providing a comprehensive set of attributes relevant to football players.

. Duplicate Check: We conducted a thorough check for duplicate records and eliminated them to ensure data consistency and integrity.

. Null Value Handling: Null values were addressed as follows:

. For continuous variables, we replaced missing values with the mean of the respective columns.
. For categorical variables, we replaced null values with the mode (most frequent value) of the columns.
. Outlier Treatment: Outliers were managed using the Interquartile Range (IQR) method:

    Values beyond the range (Q1 - 1.5 * IQR) to (Q3 + 1.5 * IQR) were identified and either removed or 
    transformed to maintain data quality.

    
# Step 3: Building a Linear Regression Prediction Model
. Data Splitting: The dataset was split into training and testing sets (80% training, 20% testing) to evaluate the model's performance.

. Linear Regression Model Creation and Training: A Linear Regression model was chosen and trained using the training data.

. Prediction and Evaluation: Using the trained model, predictions were made on the testing data. The model's performance was evaluated using metrics:

Mean Squared Error: 0.8140
Root Mean Squared Error: 0.9022
R-squared: 0.3944

# Conclusion
This project involved thorough data cleaning, preprocessing, and the creation of a linear regression predictive model for player hits.
By addressing data quality, converting data types, and building a predictive model, we aimed to provide actionable insights for The Muskets Football team. This README provides a comprehensive overview of the steps taken, from data sourcing to model evaluation.
