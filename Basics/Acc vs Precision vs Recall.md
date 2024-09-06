 ![[Pasted image 20240722150853.png]]

# Accuracy
- ratio of correctly predicted instances
$$\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}$$
# Precision
- how good the model is at predicting correct values
$$\text{Precision} = \frac{TP}{TP + FP}$$
# Recall (Sensitivity)
- ratio of correctly predicted positive instances to all actual positive instances
$$\text{Recall} = \frac{TP}{TP + FN}$$
# Balancing Recall and Precision

## F1 Score
- harmonic mean of precision and recall
- single measure to evaluate the balance between precision and recall
$$\text{F1 Score} = 2* \frac{Precision * Recall}{Precision + Recall}$$
