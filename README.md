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

| ID | Outlook | Temperature | Humidity | Windy | Play Pickleball |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 0 | Sunny | Mild | Normal | FALSE | Yes |
| 1 | Rainy | Hot | High | TRUE | No |
| 2 | Overcast | Cool | Normal | FALSE | Yes |
| 3 | Sunny | Hot | High | FALSE | No |
| 4 | Rainy | Mild | Normal | TRUE | No |
| 5 | Sunny | Cool | Normal | TRUE | Yes |
| 6 | Overcast | Hot | High | FALSE | No |
| 7 | Rainy | Cool | Normal | FALSE | No |
| 8 | Sunny | Mild | High | TRUE | Yes |
| 9 | Overcast | Mild | High | TRUE | Yes |
| 10 | Overcast | Hot | Normal | FALSE | Yes |
| 11 | Rainy | Mild | High | FALSE | No |
| 12 | Sunny | Cool | High | FALSE | Yes |
| 13 | Rainy | Hot | Normal | FALSE | No |
| 14 | Overcast | Cool | High | TRUE | Yes |

  The provided dataset functions as a structured historical log, recording environmental conditions and subsequent behavioral outcomes over a period of fifteen days. It is formatted as a standard relational table, where the rows represent individual observational records and the columns represent specific attributes of those records.

Each horizontal row within the table signifies a single, discrete event—in this case, a specific day. The leftmost column, labeled "ID," serves as a sequential index or unique identifier for each observation, beginning at 0 and concluding at 14 to establish the 15-day scope of the data.

The central columns—Outlook, Temperature, Humidity, and Windy—contain the independent variables. In predictive modeling, these are referred to as "features." These columns capture the specific meteorological conditions present on each respective day. "Outlook" categorizes the general sky condition (Sunny, Rainy, or Overcast), "Temperature" defines the thermal state (Hot, Mild, or Cool), "Humidity" specifies atmospheric moisture levels (High or Normal), and "Windy" acts as a boolean indicator (TRUE or FALSE) recording the presence of significant wind.

The rightmost column, designated "Play Pickleball," represents the dependent variable, commonly known in machine learning as the "target" or "label." This column captures the binary final outcome (Yes or No), documenting whether the activity occurred under the specific weather conditions recorded in that exact row.

When read from left to right, a single row yields a complete profile of a given day. For instance, the initial record (ID 0) documents a day characterized by a Sunny outlook, Mild temperature, Normal humidity, and a lack of wind (FALSE), culminating in a positive behavioral outcome ("Yes"). Conversely, the subsequent record (ID 1) logs a Rainy, Hot, High-humidity, and Windy day, resulting in a negative outcome ("No"). This tabular format systematically aligns environmental inputs with categorical outputs, providing the necessary structured data for algorithms to identify correlations and calculate future probabilities.

### 1. Outlook
| Outlook | Yes | No | P(Yes) | P(No) |
| :--- | :--- | :--- | :--- | :--- |
| Rainy | 0 | 5 | 0/8 | 5/7 |
| Sunny | 4 | 1 | 4/8 | 1/7 |
| Overcast | 4 | 1 | 4/8 | 1/7 |
| **TOTAL** | **8** | **7** | | |

### 2. Temperature
| Temperature | Yes | No | P(Yes) | P(No) |
| :--- | :--- | :--- | :--- | :--- |
| Cool | 4 | 1 | 4/8 | 1/7 |
| Mild | 3 | 2 | 3/8 | 2/7 |
| Hot | 1 | 4 | 1/8 | 4/7 |
| **TOTAL** | **8** | **7** | | |

### 3. Humidity
| Humidity | Yes | No | P(Yes) | P(No) |
| :--- | :--- | :--- | :--- | :--- |
| Normal | 4 | 3 | 4/8 | 3/7 |
| High | 4 | 4 | 4/8 | 4/7 |
| **TOTAL** | **8** | **7** | **8/15** | **7/15** |

### 4. Windy
| Windy | Yes | No | P(Yes) | P(No) |
| :--- | :--- | :--- | :--- | :--- |
| TRUE | 4 | 2 | 4/8 | 2/7 |
| FALSE | 4 | 5 | 4/8 | 5/7 |
| **TOTAL** | **8** | **7** | **8/15** | **7/15** |


