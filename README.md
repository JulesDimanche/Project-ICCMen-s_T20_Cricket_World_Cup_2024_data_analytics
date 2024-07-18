# Project-ICCMen-s_T20_Cricket_World_Cup_2024_data_analytics
![uh7op6arhhnprscg18mv](https://github.com/user-attachments/assets/d9732b22-f937-4732-a8fb-a012ce39eff1)
# Table of Contents :

- [Problem Statement](https://github.com/JulesDimanche/Project-ICCMen-s_T20_Cricket_World_Cup_2024_data_analytics#Problem-Statement)

* Datasource

* Data Collection

* Data Transformation

* Data Modelling

* Data Analysis Expression (DAX)

* Report

* Tools, Software and Libraries

* References

# Problem Statement :
In this project, I created a Power BI dashboard that helps review and compare the performances of all players in the T20 Men's Cricket World Cup 2022 tournament. This dashboard also enables us to select the best 11 players of the tournament based on their performance using defined selection criteria, which is included as part of the problem statement.
# Datasource :
All the data regarding matches and the World Cup was scraped from ESPNcricinfo, and details of player career performance were collected using web scraping through Python.
# Data Collection
Scraped all the data regarding matches and the World Cup and all details about players' careers using the Beautiful Soup library. Jupyter Notebook was used to convert the JSON files into dataframes and then these dataframes into CSV files for further data analysis in Power BI. 
# Data Transformation:
Performed initial data cleaning after scrapping such as player name correction, handle missing value, match id linking etc. using Pandas. Transformed the final data for dashboard using Power Query of Power BI.
# Data Modelling:
Connected all the datasets with based on some defined primary keys such as team and match ids. Also, created many measures, calculated columns and parameters for data analysis and dash boarding using DAX.
# Data Analysis Expression (DAX)
Measures used in visualization are:

Total Runs = SUM('batting_summary'[Runs])

Total Innings Batted = COUNT('batting_summary'[Match id])

Total Dismissed = SUM('batting_summary'[Out_NotOut])

Total balls faced = SUM('batting_summary'[Balls])

Strike rate = DIVIDE([Total Runs],[Total balls faced],0)*100

Boundary % = DIVIDE(SUM(batting_summary[boundary runs]),[Total Runs],0)

Boundary = SUM(batting_summary[Boundary])

Batting Position = ROUNDUP(AVERAGE(batting_summary[pos]),0)

Batting Avg = DIVIDE([Total Runs],[Total Innings Batted],0)

Avg = AVERAGE('batting_summary'[Balls])

wickets = SUM('bowling_summary'[wicket])

Total Innings Bowled = DISTINCTCOUNT(bowling_summary[Match id])

Runs Conceded = SUM('bowling_summary'[run])

Economy = DIVIDE( [Runs Conceded], ([balls Bowled]/6),0)

Dot ball % = DIVIDE(SUM(bowling_summary[Zeros]), SUM(bowling_summary[Balls]),0)

Bowling Strike Rate = DIVIDE([balls Bowled], [wickets],0)

Bowling Average = DIVIDE([Runs Conceded],[wickets],0)

balls Bowled = SUM('bowling_summary'[Balls])

Color Callout Value = if([Player Selection]="0", "#0D6ABF","#FFFFFF")

Display Text = if([Player Selection] = "1", " " ,"Select Player(s) by clicking 
the player’s name to see their individual or combined strength.")

Player Selection = if(ISFILTERED('Team summary'[Player]),"1","0") 

# Reports:
Data visualization for the dataset was done using Microsoft Power BI Desktop:
Player Analysis

**Openers**
 ![Screenshot 2024-07-18 111129](https://github.com/user-attachments/assets/5e63b676-5039-4a1a-a1d1-943669c60235)

**Middle Orders**

![Screenshot 2024-07-18 111151](https://github.com/user-attachments/assets/3b73b449-0eea-45db-ac8a-1ce4c8e0ee01)

**Finishers** ![Screenshot 2024-07-18 111236](https://github.com/user-attachments/assets/b6773bbf-3a2d-4091-8361-5c2948fbf602)

**All Rounders** ![Screenshot 2024-07-18 111249](https://github.com/user-attachments/assets/587b31f4-ff0f-4bd0-b910-451c075168fa)

**Specialist Fast bowlers** ![Screenshot 2024-07-18 111305](https://github.com/user-attachments/assets/e44938b6-c4e6-453a-a25c-5082302ad01e)

**Best Playing 11** ![Screenshot 2024-07-18 111326](https://github.com/user-attachments/assets/2b062a50-c5e0-4830-87be-271ac2fee584)

# Tools, Software and Libraries :
1.Jupyter Notebook

2.Python

3.Pandas

4.Webscraping

5.Beautifual Soup

6.Power Query Editor

7.Power BI

8.Anaconda Envirement
# References
https://codebasics.io/courses

https://www.espncricinfo.com/records/season/team-match-results/2024-2024?trophy=89

https://www.espncricinfo.com/series/icc-men-s-t20-world-cup-2024-1411166/match-schedule-fixtures-and-results

https://www.espncricinfo.com/series/icc-men-s-t20-world-cup-2024-1411166/united-states-of-america-vs-canada-1st-match-group-a-1415701/full-scorecard

