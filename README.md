# TITANIC-SURVIVAL-PREDICTION
Building a model that predicts whether a passenger on the Titanic survived or not using the Titanic dataset. This is a classic beginner project with readily available data.

"The sinking of the Titanic is one of the most infamous shipwrecks in history.

On April 15, 1912, during her maiden voyage, the widely considered “unsinkable” RMS Titanic sank after colliding with an iceberg. Unfortunately, there weren’t enough lifeboats for everyone on board, resulting in the death of 1502 out of 2224 passengers and crew.

While there was some element of luck involved in surviving, it seems some groups of people were more likely to survive than others.

In this challenge, we ask you to build a predictive model that answers the question: “What sorts of people were more likely to survive?”


Let's understand the project Step by Step:

# Understanding the Titanic Dataset:
Before delving into analysis, Let's understand the dataset. The Titanic dataset aims to predict survival based on various factors such as age, class, and ticket price. Familiarity with variables and data types is crucial for effective feature engineering.
Highlighting the importance of initial data exploration, the speaker suggests reading and understanding the dataset structure, inspecting the training data, and identifying potential variables that may influence the outcome, such as siblings onboard or parents’ presence.

# Data Exploration Techniques:
For exploring the data, checking the shape of the data, analyzing data types, and identifying null values, which is essential for cleaning and preprocessing the dataset. Understanding metrics like averages, standard deviations, and survival rates provides insights into the dataset's characteristics.
The use of visual tools like histograms and box plots can illustrate trends, such as relationships between fare prices and survival rates. This exploratory phase is crucial for identifying patterns and preparing for feature engineering afterward.

# Analyzing Numeric Variables with Histograms:
Understanding how to visualize numeric variables is essential for data analysis. Using histograms, we can observe the distribution of each variable, revealing insights into their characteristics. For instance, age shows a normal distribution, while variables such as fare do not, which suggests possible normalization for better analysis.
As we assess distributions, variables with a low number of categories, like siblings or parents, might not require normalization. However, fare shows a significant spike at lower values, prompting a reconsideration of how we handle this data.
Normalizing and scaling these variables is crucial for later modeling, especially when considering correlations between variables. This examination also aids in identifying any multicollinearity issues, where two highly correlated variables could distort our model's effectiveness.
"Understanding the distribution of variables helps identify normalization needs to prepare them for modeling."

# Correlation and Survival Analysis:
The examination of correlations serves as a foundation for understanding the relationships between variables. For example, families tend to travel together, which impacts survival rates; younger individuals and those with higher fares appear to have better survival chances.
The initial survival analysis reveals patterns, such as younger passengers having a higher likelihood to survive and those who paid more for tickets also correlating to survival. This could imply underlying social dynamics.
Survival rates also differ by categorical variables such as class, gender, and embarkation point, emphasizing the importance of classifying these factors when building predictive models.
"Analyzing how survival rates differ across groups provides pivotal insights for model development."

# Feature Engineering to Simplify Data:
Given the complexity and numerous variables within the Titanic dataset, feature engineering is a necessary step to simplify analysis and improve model performance. Initial explorations into the cabin data, which comprises letters and numbers, aim to categorize and utilize this information more effectively.
Using regular expressions to manipulate the data allows for easier classification. For example, separating cabin letters can yield insights on location and possibly survival rates. Notably, treating missing data as a categorical variable, rather than discarding it, might reveal additional information.
The ticket numbers were similarly examined. Although they appear largely unique, experimenting with included characteristics—like whether a ticket number contains letters—could provide further insights, even if the outcomes of those experiments show minimal relevance in some cases.
"Effective feature engineering allows us to distill complex datasets into manageable forms for clearer insights."

# Exploring Individual Names for Insights:
The exploration of individual names extends the investigation beyond basic demographics. Names can sometimes include titles or indicators of social standing, such as "Doctor" or "Countess," which might correlate with survival chances.
While the dataset may include a limited variety of names, further aggregation could improve insights. For instance, grouping similar titles might uncover patterns related to gender or social status and their influence on survival outcomes.
Using simple tools, such as regular expressions, allows for quick extraction and manipulation of names, setting the stage for potential refinements in future analyses.
"Further exploration of individual names can unlock additional insights into survival probabilities beyond basic demographics."

# Data Pre-processing Techniques:
For effective model preparation, it's essential to handle null values as many models do not accommodate them well. This included dropping rows with null values in the 'embarked' column and focusing only on relevant data features.
Categorical data needs to be transformed using methods like one-hot encoding, which separates categories into distinct binary columns, allowing the model to interpret them efficiently.
"You can't just have categorical variables as one chunk; they need to be in distinct columns for the model to use them."

# Strategies for Model Evaluation:
The process of evaluating model performance through cross-validation entails dividing the training set into subsets. This technique validates how well a model performs on unseen data by training it on portions of the dataset before predicting on others.
Several standard models were tested without parameter tuning to establish a baseline performance, including Naive Bayes, logistic regression, decision trees, and more. This initial exploration allows for a comparison of different algorithms' efficacy.

# Model Tuning Techniques:
A Random Forest model achieved an accuracy of around 83.5%, and an XGBoost model reached around 85.2% accuracy. However, XGBoost seemed to overfit, yielding lower performance than expected when put to the test.
"Randomized search simplifies workload and shortens analysis time while identifying effective parameters."

# Feature Importance % Analysis:
The discussion includes feature importance, which identifies which variables had the greatest impact on survival predictions in the Titanic dataset. Key features impacting survival included passenger's fare, age, gender, and class. Other features like the number of children or the presence of multiple cabins were also analyzed for their relevance.
The speaker notes that while features such as the embarkation point were considered, they appeared to be of lesser importance and could potentially confuse other models.
"Key features such as fare and age significantly impacted survival predictions."

# Voting Classifiers Exploration:
The discussion continues with the creation of voting classifiers that combine various tuned models, including K nearest neighbors, random forests, and support vector classifiers. The results suggested that while some combined models offered the best performance, the XGBoost model may have overtrained, thus hindering its effectiveness.
Further exploration involved tweaking the weights of the models in the voting classifiers to see if this would positively impact predictions. The results indicated that the original weighting was optimal, leading to the best accuracy.
"Experimentation with weighting in classifiers can yield better prediction outcomes."
