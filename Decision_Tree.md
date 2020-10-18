model1 <- rpart(classe ~ ., data=TrainTrainingSet, method="class")

prediction1 <- predict(model1, TestTrainingSet, type = "class")

# Plot the Decision Tree
rpart.plot(model1, main="Classification Tree", extra=102, under=TRUE, faclen=0)

confusionMatrix(prediction1, TestTrainingSet$classe)
## Confusion Matrix and Statistics
## 
##           Reference
## Prediction    A    B    C    D    E
##          A 1235  157   16   50   20
##          B   55  568   73   80  102
##          C   44  125  690  118  116
##          D   41   64   50  508   38
##          E   20   35   26   48  625
## 
## Overall Statistics
##                                         
##                Accuracy : 0.739         
##                  95% CI : (0.727, 0.752)
##     No Information Rate : 0.284         
##     P-Value [Acc > NIR] : <2e-16        
##                                         
##                   Kappa : 0.67          
##  Mcnemar's Test P-Value : <2e-16        
## 
## Statistics by Class:
## 
##                      Class: A Class: B Class: C Class: D Class: E
## Sensitivity             0.885    0.599    0.807    0.632    0.694
## Specificity             0.931    0.922    0.900    0.953    0.968
## Pos Pred Value          0.836    0.647    0.631    0.725    0.829
## Neg Pred Value          0.953    0.905    0.957    0.930    0.933
## Prevalence              0.284    0.194    0.174    0.164    0.184
## Detection Rate          0.252    0.116    0.141    0.104    0.127
## Detection Prevalence    0.301    0.179    0.223    0.143    0.154
## Balanced Accuracy       0.908    0.760    0.854    0.792    0.831
