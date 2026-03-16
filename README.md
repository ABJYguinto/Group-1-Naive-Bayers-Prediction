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

  The provided dataset serves as a detailed log of individual preferences, capturing how fifteen different people responded to specific environmental conditions. In this structure, the first column, labeled "ID," serves as a unique identifier for each person who participated in the survey. Numbered consecutively from 0 to 14, these IDs represent the fifteen individual respondents, ensuring that each person's specific weather preferences and their final decision are recorded on their own dedicated line.

Moving across the table, the central columns—Outlook, Temperature, Humidity, and Windy—outline the exact weather conditions presented to each individual person. These categories act as the environmental factors for the survey. "Outlook" describes the general state of the sky, such as Sunny, Rainy, or Overcast. \"Temperature" provides the thermal condition, categorized simply as Cool, Mild, or Hot. "Humidity" notes the moisture level in the air, while "Windy" is a simple true or false indicator of a noticeable breeze. Together, these four columns paint a complete picture of the specific weather environment each survey participant was asked to evaluate.

The final column on the far right, "Play Pickleball," records the ultimate choice made by each individual. After considering the unique combination of weather conditions presented in their row, the respondent provided a straightforward "Yes" or "No" answer indicating their willingness to play. By reading a single row from left to right, you can see exactly which person was surveyed, the specific weather conditions they were asked about, and the final choice they made. This layout organizes varied human opinions into a structured mathematical grid, making it possible to calculate the overall probability of the group playing under any future weather combination.

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

The provided tables represent the aggregated frequency distributions and conditional probabilities derived from the fifteen-scenario historical log. In predictive modeling, these tables act as the mathematical engine of the algorithm, summarizing the raw situational data into actionable statistical ratios.

Each table isolates one of the four environmental variables: Outlook, Temperature, Humidity, and Windy. The first two data columns, labeled "Yes" and "No," contain raw frequency counts. They tally exactly how many times a specific weather condition was present when the group ultimately decided to play or stay home. The bottom row of each table confirms the overall baseline of the dataset: across all fifteen recorded scenarios, there were exactly eight total "Yes" decisions and seven total "No" decisions.

The final two columns, "P(Yes)" and "P(No)," translate these raw counts into conditional probabilities, where the "P" stands for probability. These fractions are calculated by dividing the specific condition's frequency count by the overall total for that decision category. For example, looking at the Outlook table, the "Sunny" condition coincided with four "Yes" decisions. Because there were eight total "Yes" decisions in the entire dataset, the probability of the weather being sunny given that the group played—expressed as P(Yes)—is 4/8. Conversely, a sunny outlook only occurred on one of the seven "No" days, making its P(No) ratio 1/7.

By organizing the raw data into these specific mathematical fractions, the tables explicitly define historical behavioral trends. A review of the Outlook table reveals a 0/8 probability for the "Rainy" condition in the "Yes" column, indicating an absolute historical aversion to playing in the rain. Similarly, the Temperature table demonstrates that "Hot" conditions heavily favor a negative outcome, capturing four out of the seven total "No" decisions (4/7) compared to only one out of the eight "Yes" decisions (1/8). These calculated fractions provide the exact numerical weights the algorithm requires to compute the likelihood of playing under any future combination of weather conditions.



