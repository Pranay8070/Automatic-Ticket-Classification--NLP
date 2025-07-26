
# **Customer Complaints Classification using Topic Modeling**

## **Problem Statement**

For a financial company, **customer complaints** are critical indicators of product and service shortcomings. Efficient resolution of these complaints minimizes dissatisfaction and builds **customer loyalty**. Furthermore, analyzing complaints helps companies identify **improvement areas** to better **attract and retain customers**.

Customer complaints are often **unstructured text data**, requiring manual evaluation and categorization. As the company scales, this **manual process becomes inefficient**.

In this case study, you will work as an **NLP engineer** for a financial company aiming to **automate the customer support ticketing system**. The company offers various financial products/services such as **credit cards, banking, and mortgages/loans**.

---

## **Business Goal**

The goal is to **build a model** that can classify customer complaints based on the **product or service** they relate to. This will help the company:

* ✅ Segregate tickets into relevant categories
* 🚀 Ensure faster resolution of complaints
* 😊 Improve customer satisfaction and retention

Using **Non-Negative Matrix Factorization (NMF)**, a topic modeling approach, you will detect **patterns and recurring words** within complaints. These patterns will help identify **key features for each category**. By clustering similar complaints, the main topics of customer issues can be identified.

---

## **Approach**

You will perform **topic modeling** on the provided `.json` dataset.

Since the data is **unlabeled**, **NMF** will be applied to analyze patterns and classify tickets into **five clusters**:

1. 💳 Credit card / Prepaid card
2. 🏦 Bank account services
3. 🕵️ Theft / Dispute reporting
4. 🏠 Mortgages / Loans
5. 📂 Others

After clustering, the categorized data can be used to **train supervised models** (e.g., **Logistic Regression**, **Decision Tree**, **Random Forest**). The trained model will be capable of classifying **new incoming complaints** into their relevant categories.

---

## **Non-Negative Matrix Factorization (NMF)**

* NMF is an **unsupervised technique**, i.e., no pre-defined labels are required.
* It **decomposes** high-dimensional vectors into **lower-dimensional non-negative representations**.
* These vectors contain only **non-negative coefficients (≥ 0)**.

### ✅ In this task, we performed:

* Determined the **optimal number of clusters**
* Created **word clusters** using the best number
* **Inspected and validated** each cluster's accuracy
* **Corrected misclassified clusters**, if needed
* **Mapped clusters** to meaningful **topic names**

---

## **Supervised Models and Results**

After labeling clusters using NMF, we trained **four supervised models**. Their performance is shown below:

| **Model**           | **Accuracy** | **Precision** | **Recall** | **F1 Score** |
| ------------------- | ------------ | ------------- | ---------- | ------------ |
| Logistic Regression | 0.9200       | 0.9205        | 0.9200     | 0.9200       |
| Decision Tree       | 0.7850       | 0.7849        | 0.7850     | 0.7848       |
| Random Forest       | 0.8377       | 0.8414        | 0.8377     | 0.8332       |
| Naive Bayes         | 0.7611       | 0.7861        | 0.7611     | 0.7399       |

---

## 🏆 **Best Model: Logistic Regression**

The **Logistic Regression** model outperformed others with:

* ✅ **92% accuracy**
* 🔍 High **precision**, **recall**, and **F1 score**

### 💡 Why Logistic Regression performed best:

* Works well with **high-dimensional sparse data** (e.g., TF-IDF vectors)
* Efficiently handles **multiclass classification** using one-vs-rest strategy
* **Avoids overfitting** better than decision trees
* **Less computationally expensive** than Random Forest
* Highly **interpretable**: helps identify top contributing features (words) for each class

---

