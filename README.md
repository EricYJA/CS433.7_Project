

<h2 align="middle">CS433.7 Final Project - Transaction Prediction </h2>



### Contributor:

[Hang Zhu](https://github.com/leonzhuLGU)

[Changcheng Yuan](https://github.com/EricYJA)

Note that both contributors contributed to the project. The Github contribution is only showing submitting result. 

   

### Data Source:

You can download the dataset from the link below:

https://www.kaggle.com/c/santander-customer-transaction-prediction/data



### Environment:

* OS:  Windows 10 / MacOS Mojave 10.14.3
* Python Version: 3.6

* TensorFlow Version: 1.12.0 
* TensorBoard Version: 1.12.1
* Numpy Version: 1.16.1
* Panda Version: 0.24.1
* scikit-Learn Version: 0.20.3
* imblearn Version: 0.0
* matplotlib Version: 3.0.3

---



### Objective:

The goal for this project is to predict if a customer would make the transaction or not based on its personal data. This is vital for a company's surval cause accurate prediction would make more profit by doing more efficient resource allocation. In addition, with this prediction, the company could know who is the core user of its service and who is not. By distinguishing the core user, the company would have a better chance to gain profit. 

### Data:

The data is loaded from 2 `.csv` file from the link provided in the data source. The sample size is 200000. For each sample, there are 200 features. After some plotting, we have observed that the distribution for each of the feature is approximately normal distributed. For example, lable 0's distribution is shown below. 

  <table style="width=100%">
    <tr>
      <td>
        <img src="README.assets/lable_0.png" align="middle" width="400px"/>
        <figcaption align="middle">label_0</figcaption>
      </td>
      <td>
        <img src="README.assets/dis.png" align="middle" width="400px"/>
        <figcaption align="middle">0/1</figcaption>
      </td>
    </tr>
  </table>

For the negative/positive ratio however, the ratio is imbalanced and the negative samples is the majority. As we can see from the plot above. 

---



### Model & Code:

For our project, you can run the jupyter notebook file sequentially to view all the result or to run the `Model 1 - SVM` and `Model 2 - A Simple Neural Network` part seperately to view the result for different model. Note that for either of the model, the package loading, the data loading, and the `data processing` part are required to run before running the models. 

Note that the tensorboard graphs are stored under `graph_SVM` and `graph_NN`. To view it, change the local directory to `graph_SVM` or `graph_NN`, and then run `tensorboard --logdir ./`. 

#### SVM:

Note that for this problem, the dataset are not seperatable using a linear SVM. Hence, We implemented the nonlinear SVM totally from scratch paper using the gaussian kernel. The basic idea is to use the gaussion kernel to project the data to a higher dimension space which may make it seperatable. For the training data, we have the training result below. 

<img src="README.assets/SVM_o.png" align="middle" width="800px"/>

<img src="README.assets/SVM_g.png" align="middle" width="800px"/>

The result shows that for training data, we could reach an accuracy over 90%. However, for testing data, the accuracy is really low (we do not show the result here). By checking the data, the positive samples and the negative samples have massive intersecting area, and the dimension for each sample is very high. Therefore, our model overfitted the training data, which leads to the unpleasant result of the testing data.

#### Neural Network:

Technics we use: simple random oversampling; batch normalization; leaky relu; Adam optimizer; exponential decay of the learning rate; batch gradient decent.

This is the final model for our project. We used two hidden layers and Adam optimizer for this neural network. The detailed structure is shown in the tensorboard graph. For this model, instead of using accuracy as the metric, we choose to use the AUC as the criteria since the data is highly unbalanced (Accuracy may lie, for example, a naive model which always predict negative will get 90% accuracy). Before training, we balanced the data using simple over sampling. Compare to SVM, this modle got better performance.

<img src="README.assets/NN_o.png" align="middle" width="800px"/>

<img src="README.assets/NN_g1.png" align="middle" width="800px"/>

<img src="README.assets/NN_g2.png" align="middle" width="800px"/>

#### Conclusion

The final result we get is about 85% test AUC and 77% test accuracy. Although the accuracy is not very good compared to the naïve model, which always predict negative and get 90% accuracy, the company can get more information from our model. For naïve model, we cannot detect any customers which are willing to buy the products. However, our model successfully detects about 65% of them. Based on our model, the company can make some marketing plan to fit the need of the customers.
