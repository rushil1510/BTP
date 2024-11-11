# BTP

## Overview

This repository contains the files and code used in my B.Tech project focused on analyzing and modeling ignition time data using machine learning techniques.

## Contents

- `BTP_code.ipynb`: Jupyter Notebook containing the data processing, model training, and evaluation.
- `README.md`: This documentation file.

## Project Description

The project involves the following key steps:

1. **Data Uploading and Importing:**
   - Uploading the dataset to Google Colab and importing necessary libraries.

2. **Data Cleaning and Preparation:**
   - **Earlier Approach:**
     - Encountered a high population of zeros in the Ignition Delay Time (IDT) dataset.
     - Attempted to develop correlations while ignoring other relevant features.
     - Treated pressure (p) and equivalence ratio (φ) as constants, reducing the problem to a single-variable function \( f(x, T) \).
   - **Revised Approach:**
     - Utilized a larger dataset and removed entries with zero IDT values.
     - Applied a logarithmic transformation to the IDT values to normalize the data.
     - Enhanced data cleaning by addressing sources of error related to the initial data imbalance and feature omission.

3. **Feature Engineering:**
   - Added features such as Dropout and BatchNormalization layers to improve model generalization.
   - Implemented learning rate scheduling and early stopping to optimize training efficiency.
   - Incorporated weight decay to prevent overfitting.

4. **Modeling Approach:**
   - Utilized TensorFlow and Keras to build and train neural network models.
   - Implemented multiple activation functions, including ReLU, Leaky ReLU, ELU, SELU, Softplus, Swish, and GELU.
   - Conducted hyperparameter tuning encompassing:
     - **Solvers:** Adam, RMSprop, SGD.
     - **Activation Functions:** Exploring various nonlinearities to enhance model performance.
     - **Number of Epochs:** Determining the optimal training duration.
     - **Batch Size:** Balancing computational efficiency and model accuracy.
     - **Number of Hidden Layers:** Structuring the network depth for optimal learning.
     - **Number of Neurons per Layer:** Adjusting capacity to capture complex patterns.
   - Explored various configurations to evaluate model performance and identify optimal settings.

5. **Results Visualization:**
   - Plotted actual vs. predicted ignition times against temperature.
   - Analyzed model performance metrics, including Mean Squared Error (MSE), Root Mean Squared Error (RMSE), validation loss, and R² scores.
   - Highlighted significant findings and performance improvements achieved through methodological enhancements.

This comprehensive methodology ensures a robust and accurate modeling of ignition time data, addressing initial shortcomings and leveraging advanced machine learning techniques to yield reliable results.

## Results so far
As of now, we have the following results:
| x        | activation | optimizer | MSE        | RMSE      | val_loss    | R2         | Highlight |
|----------|------------|-----------|------------|-----------|-------------|------------|-----------|
| 0        | relu       | Adam      | 2.941561   | 1.715098  | 4.030442    | 0.581116   |           |
| 0        | relu       | RMSprop   | 0.634902   | 0.796807  | 1.038136    | 0.909589   |           |
| 0        | relu       | SGD       | 0.080952   | 0.284520  | 0.180012    | 0.988472   |           |
| 0        | leaky_relu | Adam      | 9.653893   | 3.107072  | 51.150280   | -0.374732  |           |
| 0        | leaky_relu | RMSprop   | 0.191984   | 0.438160  | 2.393225    | 0.972661   |           |
| 0        | leaky_relu | SGD       | 0.269589   | 0.519219  | 0.414715    | 0.961610   |           |
| 0        | elu        | Adam      | 1.185312   | 1.088720  | 4.588273    | 0.831209   |           |
| 0        | elu        | RMSprop   | 11.128459  | 3.335934  | 11.236115   | -0.584713  |           |
| 0        | elu        | SGD       | 9.571337   | 3.093758  | 21.364368   | -0.362976  |           |
| 0        | selu       | Adam      | 38.939394  | 6.240144  | 61.184685   | -4.545040  |           |
| 0        | selu       | RMSprop   | 0.131415   | 0.362513  | 0.098431    | 0.981286   |           |
| 0        | selu       | SGD       | 0.841084   | 0.917106  | 2.645814    | 0.880228   |           |
| 0        | softplus   | Adam      | 11.148706  | 3.338968  | 10.965772   | -0.587596  |           |
| 0        | softplus   | RMSprop   | 29.341373  | 5.416768  | 40.158642   | -3.178265  |           |
| 0        | softplus   | SGD       | 1.928846   | 1.388829  | 1.742801    | 0.725329   |           |
| 0        | swish      | Adam      | 3.353264   | 1.831192  | 6.143712    | 0.522489   |           |
| 0        | swish      | RMSprop   | 0.227470   | 0.476938  | 1.179384    | 0.967608   |           |
| 0        | swish      | SGD       | 0.062895   | 0.250789  | 0.157816    | 0.991044   | *         |
| 0        | gelu       | Adam      | 0.711756   | 0.843657  | 4.445028    | 0.898645   |           |
| 0        | gelu       | RMSprop   | 0.095453   | 0.308955  | 34.716251   | 0.986407   |           |
| 0        | gelu       | SGD       | 0.121858   | 0.349082  | 0.238294    | 0.982647   |           |
| 0.2      | relu       | Adam      | 4.483307   | 2.117382  | 14.549399   | 0.465375   |           |
| 0.2      | relu       | RMSprop   | 2.787375   | 1.669543  | 6.293042    | 0.667611   |           |
| 0.2      | relu       | SGD       | 11.588829  | 3.404237  | 27.523811   | -0.381943  |           |
| 0.2      | leaky_relu | Adam      | 0.123343   | 0.351202  | 0.418553    | 0.985292   |           |
| 0.2      | leaky_relu | RMSprop   | 23.811609  | 4.879714  | 73.472534   | -1.839484  |           |
| 0.2      | leaky_relu | SGD       | 0.066103   | 0.257105  | 0.096906    | 0.992117   | *         |
| 0.2      | elu        | Adam      | 11.988601  | 3.462456  | 67.795715   | -0.429615  |           |
| 0.2      | elu        | RMSprop   | 0.135745   | 0.368435  | 0.408682    | 0.983813   |           |
| 0.2      | elu        | SGD       | 24.505898  | 4.950343  | 54.630478   | -1.922276  |           |
| 0.2      | selu       | Adam      | 16.431276  | 4.053551  | 32.066719   | -0.959395  |           |
| 0.2      | selu       | RMSprop   | 12.516055  | 3.537804  | 42.049217   | -0.492513  |           |
| 0.2      | selu       | SGD       | 0.252323   | 0.502318  | 0.209291    | 0.969911   |           |
| 0.2      | softplus   | Adam      | 0.955154   | 0.977320  | 1.635853    | 0.886100   |           |
| 0.2      | softplus   | RMSprop   | 0.255373   | 0.505344  | 2.205143    | 0.969547   |           |
| 0.2      | softplus   | SGD       | 0.161868   | 0.402328  | 0.210299    | 0.980698   |           |
| 0.2      | swish      | Adam      | 3.942889   | 1.985671  | 4.190536    | 0.529819   |           |
| 0.2      | swish      | RMSprop   | 0.299813   | 0.547552  | 3.699860    | 0.964248   |           |
| 0.2      | swish      | SGD       | 0.248039   | 0.498035  | 0.213612    | 0.970422   |           |
| 0.2      | gelu       | Adam      | 2.555199   | 1.598499  | 7.541290    | 0.695298   |           |
| 0.2      | gelu       | RMSprop   | 14.103295  | 3.755435  | 24.844946   | -0.681788  |           |
| 0.2      | gelu       | SGD       | 15.886053  | 3.985731  | 22.035709   | -0.894378  |           |
| 0.4      | relu       | Adam      | 0.405347   | 0.636669  | 5.098900    | 0.953550   |           |
| 0.4      | relu       | RMSprop   | 1.442167   | 1.200903  | 4.892791    | 0.834738   |           |
| 0.4      | relu       | SGD       | 0.248798   | 0.498797  | 0.493081    | 0.971489   |           |
| 0.4      | leaky_relu | Adam      | 0.078747   | 0.280619  | 7.516514    | 0.990976   |           |
| 0.4      | leaky_relu | RMSprop   | 60.126319  | 7.754116  | 98.797279   | -5.890053  |           |
| 0.4      | leaky_relu | SGD       | 0.118136   | 0.343709  | 0.111626    | 0.986462   |           |
| 0.4      | elu        | Adam      | 1.126509   | 1.061371  | 2.074754    | 0.870910   |           |
| 0.4      | elu        | RMSprop   | 0.982406   | 0.991164  | 1.097237    | 0.887423   |           |
| 0.4      | elu        | SGD       | 0.060700   | 0.246374  | 0.101666    | 0.993044   |           |
| 0.4      | selu       | Adam      | 3.231121   | 1.797532  | 4.136784    | 0.629736   |           |
| 0.4      | selu       | RMSprop   | 0.453109   | 0.673134  | 4.990457    | 0.948077   |           |
| 0.4      | selu       | SGD       | 17.311469  | 4.160705  | 38.983685   | -0.983773  |           |
| 0.4      | softplus   | Adam      | 21.672568  | 4.655381  | 21.704121   | -1.483524  |           |
| 0.4      | softplus   | RMSprop   | 13.649763  | 3.694559  | 22.419928   | -0.564167  |           |
| 0.4      | softplus   | SGD       | 0.031026   | 0.176143  | 0.054062    | 0.996445   | *         |
| 0.4      | swish      | Adam      | 1.237449   | 1.112407  | 4.782214    | 0.858197   |           |
| 0.4      | swish      | RMSprop   | 0.889895   | 0.943343  | 13.806309   | 0.898024   |           |
| 0.4      | swish      | SGD       | 0.386844   | 0.621968  | 0.417619    | 0.955670   |           |
| 0.4      | gelu       | Adam      | 3.758747   | 1.938749  | 4.320956    | 0.569274   |           |
| 0.4      | gelu       | RMSprop   | 0.334768   | 0.578592  | 5.871532    | 0.961638   |           |
| 0.4      | gelu       | SGD       | 14.868752  | 3.856002  | 41.871014   | -0.703854  |           |
| 0.6      | relu       | Adam      | 4.015496   | 2.003870  | 13.565842   | 0.545697   |           |
| 0.6      | relu       | RMSprop   | 13.716484  | 3.703577  | 15.403251   | -0.551849  |           |
| 0.6      | relu       | SGD       | 18.771038  | 4.332556  | 28.804779   | -1.123708  |           |
| 0.6      | leaky_relu | Adam      | 1.416146   | 1.190019  | 2.260454    | 0.839781   |           |
| 0.6      | leaky_relu | RMSprop   | 1.213468   | 1.101575  | 1.110698    | 0.862711   |           |
| 0.6      | leaky_relu | SGD       | 25.929922  | 5.092143  | 50.046436   | -1.933647  |           |
| 0.6      | elu        | Adam      | 11.790206  | 3.433687  | 31.138079   | -0.333914  |           |
| 0.6      | elu        | RMSprop   | 14.412787  | 3.796418  | 35.165501   | -0.630627  |           |
| 0.6      | elu        | SGD       | 0.118908   | 0.344830  | 0.109702    | 0.986547   |           |
| 0.6      | selu       | Adam      | 0.342343   | 0.585101  | 0.434944    | 0.961268   |           |
| 0.6      | selu       | RMSprop   | 11.089339  | 3.330066  | 26.135836   | -0.254620  |           |
| 0.6      | selu       | SGD       | 0.237887   | 0.487737  | 0.310338    | 0.973086   |           |
| 0.6      | softplus   | Adam      | 12.414237  | 3.523384  | 24.742109   | -0.404516  |           |
| 0.6      | softplus   | RMSprop   | 6.268464   | 2.503690  | 12.474135   | 0.290802   |           |
| 0.6      | softplus   | SGD       | 1.471970   | 1.213248  | 11.997046   | 0.833465   |           |
| 0.6      | swish      | Adam      | 3.577624   | 1.891461  | 7.916812    | 0.595237   |           |
| 0.6      | swish      | RMSprop   | 0.297465   | 0.545403  | 13.147706   | 0.966346   |           |
| 0.6      | swish      | SGD       | 0.029462   | 0.171646  | 0.623092    | 0.996667   | *         |
| 0.6      | gelu       | Adam      | 12.757735  | 3.571797  | 21.003859   | -0.443378  |           |
| 0.6      | gelu       | RMSprop   | 0.981118   | 0.990514  | 0.909203    | 0.888999   |           |
| 0.6      | gelu       | SGD       | 0.179036   | 0.423127  | 4.192867    | 0.979744   |           |
| 0.8      | relu       | Adam      | 0.736898   | 0.858428  | 1.600719    | 0.911338   |           |
| 0.8      | relu       | RMSprop   | 11.385633  | 3.374260  | 18.596876   | -0.369888  |           |
| 0.8      | relu       | SGD       | 23.836176  | 4.882231  | 43.788570   | -1.867903  |           |
| 0.8      | leaky_relu | Adam      | 1.344688   | 1.159607  | 5.449129    | 0.838211   |           |
| 0.8      | leaky_relu | RMSprop   | 11.320970  | 3.364665  | 23.092503   | -0.362108  |           |
| 0.8      | leaky_relu | SGD       | 2.660031   | 1.630960  | 4.226484    | 0.679952   |           |
| 0.8      | elu        | Adam      | 3.634675   | 1.906482  | 3.700720    | 0.562686   |           |
| 0.8      | elu        | RMSprop   | 10.848038  | 3.293636  | 20.571234   | -0.305206  |           |
| 0.8      | elu        | SGD       | 12.575133  | 3.546143  | 46.498047   | -0.513005  |           |
| 0.8      | selu       | Adam      | 1.350226   | 1.161992  | 5.250858    | 0.837545   |           |
| 0.8      | selu       | RMSprop   | 0.020965   | 0.144794  | 4.970879    | 0.997478   | *         |
| 0.8      | selu       | SGD       | 10.931329  | 3.306256  | 47.340824   | -0.315227  |           |
| 0.8      | softplus   | Adam      | 0.734478   | 0.857017  | 15.800395   | 0.911630   |           |
| 0.8      | softplus   | RMSprop   | 0.113330   | 0.336645  | 0.127012    | 0.986364   |           |
| 0.8      | softplus   | SGD       | 0.234975   | 0.484742  | 0.410787    | 0.971728   |           |
| 0.8      | swish      | Adam      | 0.566709   | 0.752801  | 0.433708    | 0.931815   |           |
| 0.8      | swish      | RMSprop   | 1.176721   | 1.084768  | 5.775884    | 0.858420   |           |
| 0.8      | swish      | SGD       | 0.283973   | 0.532891  | 0.613315    | 0.965833   |           |
| 0.8      | gelu       | Adam      | 11.325455  | 3.365331  | 12.386563   | -0.362647  |           |
| 0.8      | gelu       | RMSprop   | 0.084660   | 0.290963  | 3.927773    | 0.989814   |           |
| 0.8      | gelu       | SGD       | 11.780745  | 3.432309  | 11.280348   | -0.417427  |           |
| 1        | relu       | Adam      | 7.934267   | 2.816783  | 13.178362   | -0.655283  |           |
| 1        | relu       | RMSprop   | 1.514264   | 1.230554  | 3.594475    | 0.684087   |           |
| 1        | relu       | SGD       | 6.308161   | 2.511605  | 5.184566    | -0.316038  |           |
| 1        | leaky_relu | Adam      | 9.047252   | 3.007865  | 30.694149   | -0.887479  |           |
| 1        | leaky_relu | RMSprop   | 0.391455   | 0.625664  | 2.103178    | 0.918333   | *         |
| 1        | leaky_relu | SGD       | 6.434968   | 2.536724  | 5.373157    | -0.342493  |           |
| 1        | elu        | Adam      | 64.460070  | 8.028703  | 52.619736   | -12.447956 |           |
| 1        | elu        | RMSprop   | 11.074904  | 3.327898  | 25.884327   | -1.310497  |           |
| 1        | elu        | SGD       | 8.229956   | 2.868790  | 43.951324   | -0.716971  |           |
| 1        | selu       | Adam      | 12.307677  | 3.508230  | 36.669731   | -1.567684  |           |
| 1        | selu       | RMSprop   | 9.810054   | 3.132101  | 11.539373   | -1.046619  |           |
| 1        | selu       | SGD       | 6.462926   | 2.542229  | 5.577786    | -0.348325  |           |
| 1        | softplus   | Adam      | 62.475161  | 7.904123  | 120.371216  | -12.033855 |           |
| 1        | softplus   | RMSprop   | 4.678408   | 2.162963  | 5.922301    | 0.023969   |           |
| 1        | softplus   | SGD       | 6.262274   | 2.502454  | 5.090129    | -0.306464  |           |
| 1        | swish      | Adam      | 0.900755   | 0.949081  | 2.561973    | 0.812080   |           |
| 1        | swish      | RMSprop   | 3.813006   | 1.952692  | 61.318714   | 0.204513   |           |
| 1        | swish      | SGD       | 6.001294   | 2.449754  | 4.869391    | -0.252018  |           |
| 1        | gelu       | Adam      | 0.488899   | 0.699213  | 1.320399    | 0.898004   |           |
| 1        | gelu       | RMSprop   | 0.552475   | 0.743287  | 1.396265    | 0.884740   |           |
| 1        | gelu       | SGD       | 6.506235   | 2.550732  | 5.313887    | -0.357361  |           |


## Dependencies

Ensure you have the following libraries installed:

- pandas
- numpy
- tensorflow
- matplotlib
- scikit-learn

You can install them using:

```bash
pip install pandas numpy tensorflow matplotlib scikit-learn
