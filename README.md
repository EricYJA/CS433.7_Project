# CS433.7 Final Project

<h2 align="middle">Transaction Prediction </h2>

---

###Contributor:

[Hang Zhu](https://github.com/leonzhuLGU)

[Changcheng Yuan](https://github.com/EricYJA)

Note that both contributors contributed to the project. The Github contribution is only showing submitting result. 



###Data Source:

https://www.kaggle.com/c/santander-customer-transaction-prediction/data



### Environment:

* OS:  Windows 10 / MacOS Mojave 10.14.3

* TensorFlow Version: 1.12.0 
* TensorBoard Version: 1.12.1
* Numpy: 1.16.1

---



### Objective:

The goal for this project is to predict if a customer would make the transaction or not based on its personal data. This is vital for a company's surval cause accurate prediction would make more profit by doing more efficient resource allocation. In addition, with this prediction, the company could know who is the core user of its service and who is not. By distinguishing the core user, the company would have a better chance to gain profit. 

### Data:

The data is loaded from 2 `.csv` file from the link in listed in the data source. The sample size is 200000. For each sample, there are 200 features. After testing, we have that the distribution for each of the feature is about normal distribution. For example, lable 0 is shown below. 

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

For the negative/positive ratio however, the ratio is unballanced and the negative is the majority. As we can see from the picture above. 

---



### Model & Code:

For our project, you can run the jupyter notebook file sequentially to view all the result or to run the `Model 1 - SVM` and `Model 2 - A Simple Neural Network` part seperately to view the result for different model. Note that for either of the model, the package loading, the data loading, and the `data processing` part are required to run before running the models. 

#### SVM:



#### Neural Network:



