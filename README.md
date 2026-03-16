# Group-1-Naive-Bayers-Prediction

This repository contains the dataset and probability calculations used to predict whether a group of friends will play Pickleball based on various weather conditions. The prediction model is built using the Naive Bayes machine learning algorithm, calculated from real survey data.

### Survey Responses

| Timestamp | Q1 | Q2 | Q3 | Q4 | Q5 | Q6 | Q7 | Q8 | Q9 | Q10 | Q11 | Q12 | Q13 | Q14 | Q15 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 3/15/2026 23:43:30 | No | No | Yes | No | No | Yes | No | No | No | Yes | No | No | No | No | No |
| 3/15/2026 23:43:48 | Yes | No | Yes | No | No | Yes | No | No | No | No | Yes | No | No | No | Yes |
| 3/15/2026 23:46:07 | Yes | No | Yes | No | No | Yes | No | Yes | Yes | No | Yes | Yes | Yes | No | No |
| 3/15/2026 23:47:27 | Yes | No | Yes | No | No | Yes | Yes | Yes | No | No | Yes | No | Yes | No | No |
| 3/15/2026 23:49:36 | No | No | No | No | No | No | No | No | No | No | No | No | No | No | No |
| 3/15/2026 23:53:37 | Yes | No | Yes | Yes | No | Yes | Yes | No | Yes | Yes | Yes | No | Yes | No | Yes |
| 3/16/2026 0:03:27 | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3/16/2026 0:09:09 | No | No | Yes | No | No | Yes | No | No | Yes | Yes | No | No | Yes | No | Yes |
| 3/16/2026 0:09:46 | Yes | No | Yes | No | No | Yes | Yes | No | Yes | Yes | No | Yes | No | No | Yes |
| 3/16/2026 4:23:10 | Yes | No | Yes | No | No | No | No | No | No | Yes | Yes | No | Yes | No | Yes |
| 3/16/2026 6:18:47 | Yes | No | Yes | Yes | No | Yes | Yes | No | Yes | Yes | Yes | No | Yes | No | Yes |
| 3/16/2026 7:29:02 | Yes | No | Yes | No | No | Yes | No | No | No | No | Yes | No | Yes | No | No |

---

### Question Legend (Environment Conditions)
* **Q1:** Sunny, Mild Temp, Normal Humidity, Not Windy
* **Q2:** Rainy, Hot Temp, High Humidity, Windy
* **Q3:** Overcast, Cool Temp, Normal Humidity, Not Windy
* **Q4:** Sunny, Hot Temp, High Humidity, Not Windy
* **Q5:** Rainy, Mild Temp, Normal Humidity, Windy
* **Q6:** Sunny, Cool Temp, Normal Humidity, Windy
* **Q7:** Overcast, Hot Temp, High Humidity, Not Windy
* **Q8:** Rainy, Cool Temp, Normal Humidity, Not Windy
* **Q9:** Sunny, Mild Temp, High Humidity, Windy
* **Q10:** Overcast, Mild Temp, High Humidity, Windy
* **Q11:** Overcast, Hot Temp, Normal Humidity, Not Windy
* **Q12:** Rainy, Mild Temp, High Humidity, Not Windy
* **Q13:** Sunny, Cool Temp, High Humidity, Not Windy
* **Q14:** Rainy, Hot Temp, Normal Humidity, Not Windy
* **Q15:** Overcast, Cool Temp, High Humidity, Windy




