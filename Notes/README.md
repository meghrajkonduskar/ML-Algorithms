# ML Notes
1. Overfitting - Capturing all points, Learning from everything (outliers & noise). When training errors are low but test errors are high.
2. Underfitting - Not learning anything. When trainging errors itself are very high.
3. Accuracy - No of correct predictions out of all the predictions.<br>
 $Accuracy = {(Tp + Tn) \over (Tp + Tn + Fp + Fn)}$
4. Precision - From Total number of Predicted positives how many were True positives.<br>
 $Precision = {Tp \over (Tp + Fp)}$
5. Recall - From Total number of actual positives how many were True positives. Recall is also called as sensitivity.<br>
$Recall = {Tp \over (Tp + Fn)}$
6. F1 score - Harmonic mean of Precision and Recall.<br>
    $F1\ score = {2*Precision*Recall\over Precision + Recall} $
7. Specificity - Out of total actual negatives how many were True Negatives.<br>
    $Specificity = {Tn \over Tn + Fp}$
8. Misclassification Rate - No of wrong predictions out of all the predictions<br>
    $Misclassification \  Rate = {Fp + Fn \over Fp + Fn + Tp + Tn} $
9. ROC - Reciever Operating Characteristics. TPR vs FPR graph
10. AUC - Area under Curve. auc > 0.7 - Good model
11. TPR - True Positive Rate. Total True positives out of actual positives<br>
        $TPR = {Tp \over Tp + Fn} $
12. FPR - False Positive Rate. Total False positives out of actual negatives.<br>
        $FPR = {Fp \over Fp + Tn} $
13. K-fold CV - Divide training data into 4 parts. 3 parts used for training & 1 for testing.<br>
14. Grid Search CV - Give parameters in dictionary. Grid Search CV will create model with all combination of parameters and give best result. It is very slow.
15. Randomized Search CV - Give parameters in dictionary. Randomized Search CV will create some models with random combination of parameters. It is faster than Grid Search CV.