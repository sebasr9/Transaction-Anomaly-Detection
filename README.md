
#  Transaction-Anomaly-Detection

The main goal of this project is to use machine learning to generate value for both the bank and its customers through the development of an anomaly detection model to identify unusual spending behaviour, assisting the customer support team manage risk situations.

### Modelling 

To identify abnormal spending behaviours, we opted to use the Isolation Forest algorithm due to its ability to handle large datasets and high-dimensional data, unlike other models such as LOF. This algorithm works by isolating observations through the random selection of features and calculating the path length from the root node to the termination node, serving as a measure of normality. Consequently, shorter path lengths are indicative of anomalies (developers, 2024). Given the highly imbalanced nature of the data towards the positive class (normal observations), our primary aim was to enhance the model's capability to isolate and identify the most extreme anomalies. To achieve this, we devised a custom scoring method, selecting the mean of the lowest 1% anomaly scores as our scoring target. Subsequently, we trained our model using GridSearchCV on 10% of the data to identify the optimal hyperparameters that would enable the model to effectively detect the most significant anomalies.

### Feature engineering

In order to identify abnormal spending patterns, we have opted to develop temporal features to track spending over time. This involves extracting features such as 'hours of transaction' and 'quarters' to gain a deeper understanding of trends. Furthermore, we will create a feature called 'Total_daily_spending' to capture spending patterns over time for each customer.

### Evaluation

We use an anomaly score to quantitatively evaluate the model, indicating the degree of isolation of a data point. Consequently, lower (more negative) scores signify more significant anomalies. Moreover, we opted to establish an appropriate threshold in the anomaly scores (-0.04) based on the anomaly score distribution to assist the bank in prioritizing and efficiently allocating resources to anomalies with high significance scores. Finally, to assess the qualitative aspect, we examined the relationship of variables such as 'amt', 'total daily spending', 'hours', and 'distance'. This gives us insights into the model's utility in identifying abnormal behaviour in customer spending and enabling proactive and well-informed decision-making.





