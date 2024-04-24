## Neural Network Model Report

## Overview 
The purpose of this model is to predict if applicants to the nonprofit foundation Alphabet Soup would be successful if funded. This model analyzes a dataset of over 34,000 organization that have received funding in the past. Using TensorFlow and Keras, I created and evaluated a neural network model to perform this prediction. I also tried different methods to optimize the model in an attempt to increase accuracy. All attempts yielded an accuracy score less than 75% so we can conclude that it's not guaranteed that applicants would be successful if they received fudning from Alphabet Soup. 

## Results
    ### Data Processing

        #### What variable(s) are the target(s) for your model? 
        
        The variable that was the target for the model was "y" which represented the "IS SUCCESSFUL" column in the original DataFrame. This column's values were binary numeric values           with 1 and 0 representing either successful or unsuccessful, respectively. 

        #### What variable(s) are the features for your model?

        The variable "X" represented the features for my model and was the remaining columns of the DataFrame. 

        #### What variable(s) should be removed from the input data because they are neither targets nor features?

        The variables that were removed before buliding the model were the "EIN" and "NAME" columns. The columns "APPLICATION TYPE" and "CLASSIFICATION" were preprocessed by selecting          a cutoff value for each column and replacing the overall value count with the new binned values. Binning helps with standardization by grouping values together. 


    ### Compiling, Training, and Evaluating the Model

        #### How many neurons, layers, and activation functions did you select for your neural network model, and why?

            * Layers: 2 hidden, 1 output
            * Neurons: 8 in hidden layer 1, 5 in hidden layer 2
            * Functions to activate the hidden layers: "relu"
            * Function to activate the output layer: "sigmoid"
            * Number of epochs used: 5

        These activation functions help decide whether neurons should be activated or not by calculating weighted sum and bias. This introduces non-linearity into the outputs. The              relu function, which stands for rectified linear unit, is ideal for modeling positive, nonlinear input data for classification or regression. The sigmoid function is ideal              for a binary classification dataset, in this case, whether an application was successful or not.

        #### Were you able to achieve the target model performance?

        I was not able to achieve target model performance with this model. The nn.evaluate function determined the following (rounded to 2 decimal points): 

            * Loss: 0.56
            * Accuracy: 0.72

        #### What steps did you take in your attempts to increase model performance?

        I made 3 attempts to optimize and increase model performance: 

        * Attempt 1: Added more hidden layers
            * I increased the number of hidden layers to 4 instead of 2.
            * The first 2 hidden layers had 5 neurons, the second 2 had 7. 
            * I kept the number of epochs at 5
            * Results (rounded to 2 decimal points):
                * Loss: 0.57
                * Accuracy: 0.73

        * Attempt 2: Added more neurons to hidden layers 1 and 2
            * I kept the number of hidden layers at 4.
            * The first 2 hidden layers had 10 neurons, the second 2 had 7. 
            * I kept the number of epochs at 5
            * Results (rounded to 2 decimal points):
                * Loss: 0.56
                * Accuracy: 0.73

         * Attempt 3: Added more neurons to all hidden layers
            * I kept the number of hidden layers at 4.
            * The first 2 hidden layers had 15 neurons, the second 2 had 10. 
            * I kept the number of epochs at 5
            * Results (rounded to 2 decimal points):
                * Loss: 0.56
                * Accuracy: 0.73

## Summary

Overall, each model attempt did not yield results with over 75% accuracy. Therefore, we can can conclude that it's not guaranteed that applicants would be successful if they received funding from Alphabet Soup. If I were to make additional optimization attempts, I would try preprocessing the original DataFrame differently by dropping different columns or more columns or adjusting the binning values. I could adjust the number of hidden layers and neurons per each layer. I could also adjust the number of epochs used when training the model. In conclusion, I think the model was probably underfitted with only 5 epochs and minimal neurons and would recommend increasing both to attempt to increase accuracy.
