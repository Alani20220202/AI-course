---
layout: post
title: Capstone project
author: [黃紫詅]
category: [Lecture]
tags: [jekyll, ai]
---

期末專題實作: Stock Tradeing(股票交易強化學習)

---
## Stock Tradeing(股票交易強化學習)

### 系統簡介及功能說明

1. **系統簡介**:為投資組合分配設計一個自動交易解決方案。 我們將股票交易過程建模為馬爾可夫決策過程 (MDP)，將我們的交易目標制定為最大化問題。

該算法使用深度強化學習 (DRL) 算法進行訓練，強化學習環境的組成部分是：Action . Reward function . State

•	策略包括載入資料(Load Data) . 訓練和測試(Train and  Test)  . 總結(Summarize model accuracy and Loss)

•	策略結合三種的最佳特性，從而根據不同的市場條件進行調整。

A2C：使用並行的相同Agent的副本來更新不同數據樣本的梯度。每個Agent獨立工作,與相同環境交互;

PPO：引入PPO來控制策略梯度更新，確保新策略不會與之前的策略相差太大;

DDPG：DDPG 結合了Q-learning和策略梯度的框架，並使用神經網絡作為函數逼近器。

2. **功能說明**:用深度強化學習方法集成來做自動學習股票交易策略


## RNN - Recurrent Neural Network

A recurrent neural network (RNN) is a type of artificial neural network which uses sequential data or time series data. These deep learning algorithms are commonly used for ordinal or temporal problems, such as language translation, natural language processing (nlp), speech recognition, and image captioning; they are incorporated into popular applications such as Siri, voice search, and Google Translate.

Like feedforward and convolutional neural networks (CNNs), recurrent neural networks utilize training data to learn. They are distinguished by their “memory” as they take information from prior inputs to influence the current input and output. While traditional deep neural networks assume that inputs and outputs are independent of each other, the output of recurrent neural networks depend on the prior elements within the sequence.

![32](https://user-images.githubusercontent.com/114159696/211155066-073e045e-48e2-4c1b-9bf6-2beaacbbce46.jpg)
![33](https://user-images.githubusercontent.com/114159696/211155173-64f0726a-78d0-4285-8eae-0de3850193c5.jpg)


## LSTM

LSTM(Long short-term memory)，主要由四個Component組成: Input Gate、Output Gate、Memory Cell以及Forget Gate。

![41](https://user-images.githubusercontent.com/114159696/212551726-47968235-bf30-45c9-b729-66a18c10ef1d.jpg)

Input Gate: 當將feature輸入時，input gate會去控制是否將這次的值輸入
Memory Cell: 將計算出的值儲存起來，以利下個階段拿出來使用
Output Gate: 控制是否將這次計算出來的值output
Forget Gate: 是否將Memory清掉(format)，有點restart的概念。
其中，“是否”這件事情，是可以透過神經網路進行學習。

接下來我們可以更近一步去看數學表示方式：

![42](https://user-images.githubusercontent.com/114159696/212551929-dabe7984-952d-4435-ac59-1a7111126715.jpg)


**ANN - Artificial Neural Network**

Artificial Neural Networks (ANN) are multi-layer fully-connected neural nets that look like the figure below. They consist of an input layer, multiple hidden layers, and an output layer. Every node in one layer is connected to every other node in the next layer. We make the network deeper by increasing the number of hidden layers.

![21](https://user-images.githubusercontent.com/114159696/211153880-f5ba4b5a-a468-4abf-9fc0-78a62aff3165.jpg)

![22](https://user-images.githubusercontent.com/114159696/211153882-5c20f748-62a7-4d12-bf98-e07f916d134a.jpg)

A given node takes the weighted sum of its inputs, and passes it through a non-linear activation function. This is the output of the node, which then becomes the input of another node in the next layer. The signal flows from left to right, and the final output is calculated by performing this procedure for all the nodes. Training this deep neural network means learning the weights associated with all the edges.

The equation for a given node looks as follows. The weighted sum of its inputs passed through a non-linear activation function. It can be represented as a vector dot product, where n is the number of inputs for the node.
![23](https://user-images.githubusercontent.com/114159696/211153883-630a5144-3ee6-4528-9dce-406d478838bc.jpg)

Common activation functions

An activation function determines whether a neuron should be activated. The nonlinear functions typically convert the output of a given neuron to a value between 0 and 1 or -1 and 1. Some of the most commonly used functions are defined as follows:

Sigmoid: This is represented with the formula g(x) = 1/(1 + e^-x).

![24](https://user-images.githubusercontent.com/114159696/211153887-71c92b56-0b6b-45ae-a39a-e06e77c64b6f.jpg)

Tanh: This is represented with the formula g(x) = (e^-x - e^-x)/(e^-x + e^-x)

![25](https://user-images.githubusercontent.com/114159696/211153888-99b58178-f936-4e49-84b5-667e61c0f7ab.jpg)

Relu: This is represented with the formula g(x) = max(0 , x)

![26](https://user-images.githubusercontent.com/114159696/211153890-8de8be3e-2326-40b4-8dcb-428078954d24.jpg)



---
### 系統方塊圖
系統流程圖<br>
![11](https://user-images.githubusercontent.com/114159696/211050535-6bda335c-177e-44e6-aca6-d5c107e14838.jpg)

AI模型說明<br>
![12](https://user-images.githubusercontent.com/114159696/211053031-c8a23ab4-185e-47f6-a08c-356f06ffdde7.jpg)

---
### 製作步驟
1. 下載股票資料
2. 建立資料集 dataset
3. 移植程式to Kaggle
4. Kaggle上訓練模型
5. Kaggle上測試模型

---
### 系統測試
**1.Load Tesla data**

Dataset contains following fields

•Date - Each trading day

•Open - Open price of stock

•High - High price of stock in the particular day

•Low - Low price of the stock in the particular day

•Close - Close price of the stock at end of the day

•Adj Close - Adjusted close price of stock 

•Volume - Volume traded in the entire day

![13](https://user-images.githubusercontent.com/114159696/211050541-aa75cc12-2067-476c-94e7-581c375b1cda.jpg)

**2. EDA on Tesla Data**

Plotting Few OHLC data

![14](https://user-images.githubusercontent.com/114159696/211050544-613a431c-ce18-4c23-a188-0ef0afd6f667.jpg)

**3. Significance of ACF and PACF**

Autocorrelation Function (ACF)

![19](https://user-images.githubusercontent.com/114159696/211153235-e064f178-5568-4287-83a8-c9fc94ef50fa.jpg)

Partial Autocorrelation Function (PACF)

![00](https://user-images.githubusercontent.com/114159696/211153324-ec788618-1f62-4ed4-b82d-4701ad097029.jpg)

Univariate - Time series forecasting

![20](https://user-images.githubusercontent.com/114159696/211153538-ea7df2b0-e7ab-4855-b546-a602ff7263ce.jpg)


**Automatically select Lag value from PACF graph**

![27](https://user-images.githubusercontent.com/114159696/211154226-5a109992-f817-402b-ac4c-9b479e759015.jpg)

**Build an MLP model**

•Sequential() - The sequential API allows you to create models layer-by-layer

•add() - To create a Sequential model incrementally via the add() method

•Dense() - To add a stack of fully connected layer (either a hidden layer or an output layer)

•input_dim - To specify the input shape

•Activation - Decides the output a node. The purpose of the activation function is to introduce non-linearity into the output of a neuron.

•Loss function - The function we want to minimize or maximize is called the objective function or criterion. When we are minimizing it, we may also call it the cost function, loss function, or error function.

•Optimizer - Minimizing the loss function, by changing the parameters (weights and biases)

![28](https://user-images.githubusercontent.com/114159696/211154474-3e998ddd-007a-45b8-8456-b0e8389a0485.jpg)

**Fit data to Model**

![29](https://user-images.githubusercontent.com/114159696/211154617-fc61aa50-28d5-4722-a16b-efb897054084.jpg)

### 成果展示

**KAGGLE**:https://www.kaggle.com/code/alani20220202/time-series-forecasting-tesla-stock?scriptVersionId=116430236

**Train and  Test**

![30](https://user-images.githubusercontent.com/114159696/211154759-2831b13e-7dac-4fc5-8883-b188f1a64a5d.jpg)

![15](https://user-images.githubusercontent.com/114159696/211050548-ed4c8aff-be5f-4bd4-abd2-3f1880743306.jpg)


**Plot Actual Test data and Predicted Data**

![31](https://user-images.githubusercontent.com/114159696/211154922-3864b0bc-8340-40a3-ba7c-a53217db06c5.jpg)
![16](https://user-images.githubusercontent.com/114159696/211050550-0506a59f-ea2d-4752-8564-f8b18995c71f.jpg)

**Summarize model accuracy and Loss**

![34](https://user-images.githubusercontent.com/114159696/211155253-dc6c6db3-09d0-43d8-be92-f750352e2d83.jpg)

![17](https://user-images.githubusercontent.com/114159696/211050554-000cc962-987f-4760-b95b-e15b443a4f3b.jpg)

![35](https://user-images.githubusercontent.com/114159696/211155294-86f59881-4c75-42a9-8039-a11dfb23c2c3.jpg)

![18](https://user-images.githubusercontent.com/114159696/211050556-5daab456-ca82-4039-9fbd-9e1ca2f5688a.jpg)
### 總結
可以藉由分析股票交易，最大化投資績效-例如預期回報，預期回報最大化可以基於對潛在回報和風險的估計獲得，這在復雜多變的股票市場中，設計盈利策略具有挑戰性，揭示一種深度強化學習方案，該方案通過最大化投資回報來自動學習股票交易策略。

