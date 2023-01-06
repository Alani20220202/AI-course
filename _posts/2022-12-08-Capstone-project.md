
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

1. **系統簡介**:•	策略包括載入資料(Load Data) . 訓練和測試(Train and  Test)  . 總結(Summarize model accuracy and Loss)

•	策略結合三種的最佳特性，從而根據不同的市場條件進行調整。

A2C：使用並行的相同Agent的副本來更新不同數據樣本的梯度。每個Agent獨立工作,與相同環境交互;

PPO：引入PPO來控制策略梯度更新，確保新策略不會與之前的策略相差太大;

DDPG：DDPG 結合了Q-learning和策略梯度的框架，並使用神經網絡作為函數逼近器。


2. **功能說明**:用深度強化學習方法集成來做自動學習股票交易策略

---
### 系統方塊圖
系統流程圖<br>
![11](https://user-images.githubusercontent.com/114159696/211050535-6bda335c-177e-44e6-aca6-d5c107e14838.jpg)

AI模型說明<br>
![22](https://user-images.githubusercontent.com/114159696/211050539-a34e25b6-50ae-4894-8fc8-dbdcc99f730c.jpg)

---
### 製作步驟
1. 下載股票資料： download_stock_quote.py
   git clone https://github.com/rkuo2000/tf
   cd tf
   pip install alpha_vantage
python download_stock_quote.py MSFT
2. 建立資料集 dataset
   移植程式to Kaggle
3. Kaggle上訓練模型
4. Kaggle上測試模型

---
### 系統測試及成果展示
**Load Tesla data**

![33](https://user-images.githubusercontent.com/114159696/211050541-aa75cc12-2067-476c-94e7-581c375b1cda.jpg)

![44](https://user-images.githubusercontent.com/114159696/211050544-613a431c-ce18-4c23-a188-0ef0afd6f667.jpg)

**Train and  Test**
![55](https://user-images.githubusercontent.com/114159696/211050548-ed4c8aff-be5f-4bd4-abd2-3f1880743306.jpg)

![66](https://user-images.githubusercontent.com/114159696/211050550-0506a59f-ea2d-4752-8564-f8b18995c71f.jpg)

**Summarize model accuracy and Loss**
![77](https://user-images.githubusercontent.com/114159696/211050554-000cc962-987f-4760-b95b-e15b443a4f3b.jpg)

![88](https://user-images.githubusercontent.com/114159696/211050556-5daab456-ca82-4039-9fbd-9e1ca2f5688a.jpg)
### 總結
可以藉由分析股票交易，最大化投資績效-例如預期回報。預期回報最大化可以基於對潛在回報和風險的估計獲得。這在復雜多變的股票市場中，設計盈利策略具有挑戰性。揭示一種深度強化學習方案，該方案通過最大化投資回報來自動學習股票交易策略。

