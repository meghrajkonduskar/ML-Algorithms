# ML Notes
1. Overfitting - Capturing all points, Learning from everything (outliers & noise). When training errors are low but test errors are high.
2. Underfitting - Not learning anything. When trainging errors itself are very high.
3. Accuracy - No of correct predictions out of all the predictions.
    $$Accuracy = {(Tp + Tn) \over (Tp + Tn + Fp + Fn)}$$
4. Precision - From Total number of Predicted positives how many were True positives.
    $$Precision = {Tp \over (Tp + Fp)}$$
5. Recall - From Total number of actual positives how many were True positives. Recall is also called as sensitivity.
    $$Recall = {Tp \over (Tp + Fn)}$$
6. F1 score - Harmonic mean of Precision and Recall.
    $$F1\ score = {2*Precision*Recall\over Precision + Recall} $$
7. Specificity - Out of total actual negatives how many were True Negatives.
    $$Specificity = {Tn \over Tn + Fp}$$
8. Misclassification Rate - No of wrong predictions out of all the predictions
    $$ Misclassification Rate = {Fp + Fn \over Fp + Fn + Tp + Tn}
9. ROC - Reciever Operating Characteristics. TPR vs FPR graph
10. AUC - Area under Curve. auc > 0.7 - Good model
11. TPR - True Positive Rate. Total True positives out of actual positives
        $$ TPR = {Tp/Tp + Fn}$$
12. FPR - False Positive Rate. Total False positives out of actual negatives.
        $$ FPR = {Fp/ Fp + Tn} $$
