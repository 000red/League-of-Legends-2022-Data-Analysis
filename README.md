# League of Legends 2022 Data Analysis
Project for DSC80 at UCSD

---

## Introduction
In this analysis, we will be working with a dataset that contains statistical information on competitive matches in the popular online multiplayer game, League of Legends (LoL), specifically from the year 2022. By studying this dataset, we can gain valuable insights into different aspects of gameplay and explore potential connections between two important factors: the number of wards placed by players and the amount of damage they dealt. Our goal is to deepen our understanding of strategic gameplay elements and how they impact individual performance within the game.

Relevance and Significance:
There are several reasons why readers should find this analysis interesting. Firstly, League of Legends boasts a large and dedicated player base, along with a thriving professional esports scene. For both professional players and casual enthusiasts looking to enhance their skills, understanding the relationship between specific gameplay actions, such as ward placement and damage dealt, can provide valuable insights.

Additionally, exploring the correlation between wards placed and damage dealt can shed light on the strategic decision-making process in the game. Wards are vital tools for controlling vision, enabling players to gather information about enemy movements and potentially make game-changing plays. On the other hand, damage dealt reflects a player's offensive capabilities. Investigating the connection between these two variables can reveal patterns in how players utilize vision and its impact on their overall performance.

Dataset Details:
The dataset consists of a total of 149400 rows, each representing a unique match with up to 12 rows (5 for each player on each team and 2 for the summary of each team in the match) from the 2022 competitive season of League of Legends. Our analysis will focus on the following key columns:

Player ID: An exclusive identifier for each player.
Game ID: A unique identifier for each match.
Wards Placed: The number of wards placed by a player in a specific match.
Damage Dealt to Champions: The total amount of damage inflicted by a player during a match.

By examining the relationship between the "Wards Placed" and "Damage Dealt to Champions" columns, we will explore whether there is a correlation between the number of wards placed by players and the damage they were able to inflict in matches.

---

## Cleaning and EDA
To ensure the accuracy of our analysis, we conducted several data cleaning procedures on the dataset. These procedures involved eliminating irrelevant rows and eliminating any missing or null values in the pertinent columns.

To filter out unnecessary rows, we focused on the relationship between wards placed, damage dealt, and teams. We accomplished this by considering the "Position" column and retaining only the rows where the position was labeled as "team." This enabled us to work with aggregated data at the team level rather than individual player-level data.

To address null values, we examined the "Wards Placed" and "Damage Dealt to Champions" columns. Rows containing null values in these columns were eliminated from the dataset. Null values can arise from incomplete or missing data, and by removing these rows, we ensured that our analysis is based on complete information regarding wards placed and damage dealt by teams.

Through these data cleaning procedures, we successfully generated a cleaned DataFrame that exclusively consists of relevant rows and does not contain any missing values in the columns of interest.

Below is a preview of the head of the cleaned DataFrame:

| gameid                | position   | teamname                      |   damagetochampions |   wardsplaced |
|:----------------------|:-----------|:------------------------------|--------------------:|--------------:|
| ESPORTSTMNT01_2690210 | team       | Fredit BRION Challengers      |               56560 |            74 |
| ESPORTSTMNT01_2690210 | team       | Nongshim RedForce Challengers |               79912 |            93 |
| ESPORTSTMNT01_2690219 | team       | T1 Challengers                |               59579 |           119 |
| ESPORTSTMNT01_2690219 | team       | Liiv SANDBOX Challengers      |               74855 |           129 |
| 8401-8401_game_1      | team       | Oh My God                     |               40086 |            79 |


### Univariable Graphs

<iframe src="assets/section1_1.html" width=800 height=600 frameBorder=0></iframe>

Histogram showing the frequency of damage to champaions within certain 100 bins which seems to show a normal distribution curve.

<iframe src="assets/section1_2.html" width=800 height=600 frameBorder=0></iframe>

Histogram showing the frequency of damage to champaions within certain 60 bins which seems to show a normal distribution curve.

<iframe src="assets/section1_3.html" width=800 height=600 frameBorder=0></iframe>

Scatter plot of damage to champions and wards placed which shows a positive correlations between the two values.

<iframe src="assets/section1_4.html" width=800 height=600 frameBorder=0></iframe>

---

## Assessment of Missingness

For our NMAR analysis, based on the provided dataset, we believe the "Double Kills" column could potentially be considered as NMAR (Not Missing At Random). The reason behind this assumption is that there are certain regions in competitive LoL that do not consistently report or track double kills, resulting in missing values (null) for some teams.

<iframe src="assets/section2_1.html" width=800 height=600 frameBorder=0></iframe>


<iframe src="assets/section2_2.html" width=800 height=600 frameBorder=0></iframe>


---

## Hypothesis Testing

Null Hypothesis: There is no correlation between wards placed and damage dealt by teams in the League of Legends dataset.

Alternative Hypothesis: There is a positive correlation between wards placed and damage dealt by teams in the League of Legends dataset.

Test Statistic: 0.5119240614648413

P-value: 0.0

Conclusion: Based on the analysis using a significance level of 0.05, the p-value of 0.0 is less than the chosen significance level. Therefore, we reject the null hypothesis and conclude that there is a statistically significant positive correlation between wards placed and damage dealt by teams in the League of Legends.
