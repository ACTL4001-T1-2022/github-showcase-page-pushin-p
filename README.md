# Team Pushin-P
Contributors: Raphael Tay, Romman Ahmend, Gurkanwal Singh, Jason Tu, Dilmith Wickramanayake

# Table of Contents
- [Project Outline](#project-outline)
- [Team Selection](#team-selection)
    + [Data Analysis Methods](#data-analysis-methods)
    + [Significant Characteristics](#significant-characteristics)
    + [Model Selection](#model-selection)
    + [Considerations and Justifications](#considerations-and-justifications)
- [Economic Impact](#economic-impact)
- [Implementation Plan](#implementation-plan)
      - [Implementation Timeline](#implementation-timeline)
    + [Team Selection](#team-selection-1)
    + [Financial Performance](#financial-performance)
    + [Economy](#economy)
- [Assumptions and Data Limitations](#assumptions-and-data-limitations)
- [Risk and Risk Mitigation](#risk-and-risk-mitigation)
    + [Interest Rate and Inflation Fluctuations](#interest-rate-and-inflation-fluctuations-1)
    + [Competition Fines](#competition-fines-1)
    + [Retention Rate of Players](#retention-rate-of-players-1)
    + [Reputational Risk](#reputational-risk-1)
    + [Sensitivity Impact](#sensitivity-impact)
- [References](#references)

# Project Outline
Football is an internationally recognised sport that crosses all ethnic and religious boundaries over the world. This report explores how Rarita, a country that wishes to qualify for the FSA League within 5 years in the “world of international football”. It explores the project’s objectives of creating a competitive national football team through data exploration and manipulation, to best optimise the probability of qualification through Monte Carlo simulation measures. Moreover, it details how the successful completion of the national football brand will affect Rarita’s economy over the next 10 years through a boost in global visibility and recognition of being a competitive team. However, assumptions about the model are prevalent and are also explored in this report. Moreover, the report also drafts an implementation timeline to rollout objectives of building and sustaining a competitive team and using this success to grow Rarita’s global visibility and economy.

# Team Selection
Although the dataset presented numerous factors of player skills and attributes, data exploration and modelling indicated that pass completion is most correlated with the highest probability of winning in a competitive league. 
### Exploratory Data Analysis
There were some key trends in the data when analysing specific metrics by player position. We noticed a unique clustering behaviour for selected players (see appendix 4). This aligned with our hypothesis, that consistency and reliable results were rewarded with team selection. Therefore, looking to select players who neither outperformed nor underperformed significantly enabled finding the location of good consistent performers.

#### Figure 1: Clustering pattern of selected players vs universe
![Screenshot 2022-04-11 154415](https://user-images.githubusercontent.com/102013523/162672376-bbec044e-eedb-40d7-b38c-4d52d72778b2.png "% Holding Tackles")

### Data Analysis Methods
Furthermore, omitting modelling methods that did not perform cluster-based analysis particularly well such as linear and polynomial regression, the focus was placed on gradient boosting, random forest and principal component analysis. K-Nearest-Neighbours was also considered, but as it only analyses two factors at a time, we also deemed it unsuitable for our purposes as there are multiple factors to consider.

### Significant Characteristics
Since soccer is a team sport, we sought to identify patterns or groupings of factors that contribute to that elusive winning team formula. As a player’s position on the pitch affects their role in a match, we decided to isolate and identify trends of selected players by their main or preferred pitch positions. This analysis showed that, unsurprisingly, the most important skills for each position were dependent on their specific roles in the squad. 

#### Figure 2: Variables of importance for FWs, notice most are defensive stats because FWs rarely take up much of the defensive burden.
![image](https://user-images.githubusercontent.com/102013523/162672036-82d796fe-f808-409d-a175-43e8494553c6.png "Importance 1")
#### Figure 3: Important variables for Midfield players, notice that most variables are related to passing.
![image](https://user-images.githubusercontent.com/102013523/162672431-89dd8df1-11a1-4b78-af18-878aa9a83fa1.png)
#### Figure 4: Variables important in determining selection of Defenders, notice that majority are pass statistics as defenders play a vital role in the build-up of play often sending the ball forward.
![image](https://user-images.githubusercontent.com/102013523/162672475-7d65399a-e34d-46db-94af-28eb16046789.png)
#### Figure 5: Important variables for Goalkeeper selection
![image](https://user-images.githubusercontent.com/102013523/162672513-43b38b78-4dac-4965-960f-a4943df13b16.png)

The above charts show the most important characteristics for each pitch position. Noticeably, passing statistics seem to hold the most importance.

### Model Selection
After running through the various models such as bagging, principal component analysis (PCA), random forest and gradient boosting, we identified that gradient boosting was the most accurate model at classifying players into selected and not selected as seen in table below. Additionally, we noticed an imbalance in the data for the response. As imbalanced data introduces skewness into the model, we eliminated this bias by conducting both random over- and under-sampling to balance our dataset. 

#### Figure 6: Accuracy against test set for various models
![Screenshot 2022-04-11 154807](https://user-images.githubusercontent.com/102013523/162672684-71b28ea3-240f-4090-81f5-7a7c95a73f62.png)

### Players Selected from Model

| Player | Position | Salary |
| :-: | :-: | :-: |
| J. Dahiru | Defender | ∂ 19,090,000 |
| A. Núñez | Defender | ∂ 22,730,000 | 
| Y. Thungu| Defender | ∂ 26,070,000 | 
| K. Nalwanga | Defender | ∂ 5,110,000 | 
| T. Larsson | Defender | ∂ 1,140,000 | 
| E. Afolabi | Forward | ∂ 3,190,000 |
| A. Mtambo | Defender | ∂ 6,520,000 | 
| T. Monteiro | Defender | ∂ 4,120,000 | 
| H. Makumbi | Forward | ∂ 7,430,000 | 
| Z. Cumbe | Midfielder | ∂ 7,250,000 | 
| D. Lehner | Midfielder | ∂ 6,730,000 |
| P. Rabiu | Midfielder | ∂ 7,280,000 |
| A. Kyarikunda | Forward | ∂ 8,870,000 |
| Z. Zziwa | Forward | ∂ 9,120,000 |
| D. Baah | Midfielder | ∂ 3,610,000 |
| F. Ajio | Forward | ∂ 1,990,000 |
| D. Mattila | Midfielder | ∂ 18,500,000 |
| E. Nakanjako | Midfielder | ∂ 10,750,000 |
| W. Nasiru | Goalkeeper | ∂ 22,410,000 |


### Considerations and Justifications
A major consideration in the model selection process was the interpretability of results, as specific groupings of factors needed to be identified. Gradient boosting models (GBMs) had a reasonable degree of accuracy, compared to other models, but were weaker than random forests in terms of interpretability. However, as accuracy was a key focus in the selection process, GBMs were preferred. There were also significant limitations to the data, in particular missing information, and the limited amount of historical data made comparisons and benchmarking of results difficult. As such, it represented a huge consideration, in particular the specific treatments for each section of missing data.

# Economic Impact
Based on the assumption that the team selection would yield a competitive team instantly, the revenue for Football in Rarita was assumed to meet the expected value of the average competitive teams which have been top 10 consistently within 2020 and 2021. Along with the assumption that expenses remain at an equal ratio to revenue as additional revenue will be reinvested within the league, the revenue and expenses projections are displayed in the graph below.

#### Figure 7: Revenue & Expenses Forecast over the next 10 years
![image](https://user-images.githubusercontent.com/102013523/162672787-e73f3297-2c50-4048-8573-b2a24fdbb289.png)

The NPV Model (Appendix 2C) estimates a net present value of **∂14.2 billion** for the project over the **next 10 years** which would account for around **5% of the 2020 GDP** with the implementation of a consistent top 10 Raritan national football team. Hence, although it is difficult to issue a quantifiable link with GDP increase, a self-sufficient football league with a national presence will have positive influences on GDP and GNI per capita as there will be higher fiscal stimulation within the domestic economy as well as global investments.  

There’s a significant correlation between teams that win soccer tournaments or are hosts of tournaments with growth in the economy. Observing historical observations for the World Cup, winners see an “average increase of **1.6%**” (AP News, 2022) in GDP compared to the previous year. Also, winning a World cup is known to produce a surge of national pride that influences consumer behaviour. However, the effects of this are often short-term, and is akin to a ‘sugar rush’ for the economy, with the economy contracting in subsequent years. Being the host of the tournament also boosts the GDP due to additional jobs being created for the construction of stadiums and expanded infrastructure. Similarly, hosting only has short term implications as once the tournament ceases, new jobs and construction are no longer in demand, and tourism wanes. Therefore, Rarita should consider a long-term analysis for profitability, by considering the longevity of stadiums, national spirits, as well as international awareness of the host country to boost seasonal tourism. 

#### Figure 8: Population Split between West, East & Central Rarita
![image](https://user-images.githubusercontent.com/102013523/162672852-b4018483-5998-4e62-a274-78c3b94b3384.png)


As we can see from figure 8, most of the population is located within West Rarita as more than 60% of the total population can be accounted for within Rarita’s West. However, on the other hand, figure 9 depicts that the gross national income for West Rarita is approximately half per capita relative to East Rarita which highlights a major wealth discrepancy between the geographic regions. The introduction of a national football team will lead to higher global visibility and will secure higher investments which will benefit West Rarita specifically with additional employment and income opportunities.

#### Figure 9: GNI Per Capita for each region within Rarita
![image](https://user-images.githubusercontent.com/102013523/162672908-3920fe88-8f24-4d02-b189-73498ceeb8cd.png)


Furthermore, healthcare spending and the household saving rate can be seen to be similarly proportioned (Appendix 2B) between the regions and both are linked to the state of the economy. Since both household savings rate and health care spending scale with disposable income (equal to GNI), it is appropriate that higher disposable income would yield to higher statistics. As a result, we can assume that the economic boost because of the league’s expansion will benefit to reduce the economic gap between East and West Rarita.

# Implementation Plan
#### Implementation Timeline
![image](https://user-images.githubusercontent.com/102155069/162667383-66eff15b-d82e-4d9d-9f94-a792847b403f.png "Implementation TimelIne")
### Team Selection
With both the initial sum and projected revenues being ample to cover player wages, the 19 selected players will slot into the team from the first year of implementation (2022).  The team will be analysed yearly, using end of year FSA League standings as the metric – ensuring the team stays on course to reach its competitive targets. 
Until the top 10 target is achieved (predicted 2024), contracts will be one-year terms, allowing for flexibility in team changes, and maximising team potential. Once this target is achieved, contracts will be extended to 3 years, to sustain team stability and build towards winning the tournament. 
### Financial Performance
In terms of revenue, there are 3 main sources – matchday, broadcast and commercial – as well as a supplement from loan fees. The Raritan Football Association will have to establish a loan structure, where players between the median and upper quartile will be loaned out, likely to unestablished teams also looking to enter the FSA. It is expected that those below the median will not have the quality to attract loans.  

The essential measure of financial performance is to determine if, by the end of 2024, the can hit its revenue metric targets of 65.7 doubloons/capita, 146.4 doubloons/capita and 202.48 doubloons/capital respectively for matchday, broadcast and commercial revenue. These numbers, if achieved, will reflect Rarita earning a similar level of revenue to the current top teams, once it is established amongst them.  
### Economy
Further, the increased broadcast revenue reflects the increased global visibility of Rarita, as this broadcast revenue is increasing as more people around the world tune in to watch the Raritan team play. Additionally, the impact of increased visibility can be seen in increased matchday revenue, with it expected to increase as more tourists come to watch games and pay premium ticket prices. The garnered tourists will require accommodation and services, and are likely to visit other Raritan attractions, thereby boosting the inflow of money across several economic sectors.
Global visibility will be further monitored using the metric of social media followers, with Facebook followers expected to hit the top team current average of 65 million, and Instagram followers to reach 49.6 million by 2024, in line with all forecasts of Rarita truly establishing itself as a top team by then. Every two years, follower numbers will be reviewed, to determine whether they match expectations of growing in line with attendance growth. 

# Assumptions and Data Limitations
| Data Limitation | Assumptions | Justification |
| :-: | :-: | :-: |
| Only provided data on tournament rankings for 2 years (2020 and 2021), but economic data is from 2016-2020 | Assumed that the top 10 teams across the 2 years were also the top 5 teams across the 2016-2020 period. | Allows analysis of the economic impact of being a top 10 team. Without assumption, there is no link between tournament rankings and economic data. | 
| No information given on which countries the leagues (other than RFL) pertain to. | Only league in Rarita is RFL. | Other leagues have no given connection to Rarita. Further, the assumption allows analysis of team revenues and expenses in Rarita. | 
| No information given on the quality of different leagues. | All leagues are of equal quality, so statistics across different leagues hold equal value. | Allows fair comparison between players in different leagues. |
| No information given on the population of other countries | Football is similarly popular across Rarita and the top 5 countries, Raritan attendances will reach similar levels once Rarita achieves a similar level of success. | Allows analysis of the impact of international football success on Rarita’s attendance, and thus future revenues/expenses.
| No explanation given for negative values for statistics such as: 	Goals & Shots, Penalties,	Key Passes & Assists,	1/3 passes,	Tackles, Pressures & Blocks,Saves| Goals & Shots: negative due to subtracting own goals and shots on own goal, Penalties: negative due to subtracting penalties conceded by a player, Key Passes & Assists: negative due to subtracting passes that directly lead to an opposition goal, 1/3 passes: negative due to subtracting | Without an explanation of these strangely negative statistics, the figures cannot be analysed, which would severely limit the pool of players that we could test our model on. |
| Complete data only on 2021 Tournament statistics | 2021 Tournament statistics (and related league statistics) are accurate reflections of players’ abilities. | Without any indications of past performance, there is no way to determine if these statistics reflect normal playing ability, or a momentary form improvement. The assumption allows us to analyse players’ stats equally. |

# Risk and Risk Mitigation

![image](https://user-images.githubusercontent.com/102013523/162673124-c8151e50-ec0e-4568-b99c-bf8fe0e1e1fc.png)
### Interest Rate and Inflation Fluctuations 
By assuming the Raritan government conducts monetary policy to bound inflation within comfortable levels, it is doubtless there may be circumstances where this is unsuccessful. Interest rates and inflation are inversely proportional to each other and as such there will be trade-offs of loan players with our funds. Our funds may not have the same purchasing power as in the past and moreover, interest rates may drive up the fee payments on these loans. 

Mitigant: Hedge against inflation through investing our funds in asset classes that track an index with a rate higher than the inflation level. 

### Competition Fines 
In the international spotlight, Rarita will likely encounter fines for breach of guidelines and regulations within the international sporting organisation. Fines issued may cause a backlog of future objectives and bottleneck the successful plan of being competitive within 10 years. 

Mitigant: To mitigate the impact of fines, Rarita may consider using buffers in their budget to offset potential fines. They can hold reserves with a certain proportion to account for such event. 

### Retention Rate of Players
To develop Rarita’s team dynamics and competitiveness over their tenure in the league, it is preferred that player retention is long term and a relatively stable figure each year. In its early formation, retaining players that are well synergised is beneficial to reducing time spent on team building, as well as strengthening these players’ dynamics within the team over time. Since it is unlikely that the team will win within the first few years, focusing on developing strong players will provide a competitive edge for Rarita in the long term. 

Mitigant: Provide monetary incentives from the budget to well-synergised players to be retained for the following league year.  

### Reputational Risk
Rarita’s reputation within the sporting community can be influenced by whether it is successful or not in the league. Reputational risk can be determined by whether Rarita’s reputation exceeds its true character, how much external beliefs and expectations change, and quality of internal coordination (Eccles, Newquist and Schatz, 2007). Moreover, reputational damage to the organisation may cause decreased funding and weaken traction of potential tourism and economic benefit in the future. 

Mitigant: Conduct regular surveys with fans to measure engagement and satisfaction with the organisation. Close gaps of misconceptions through creating a public relations team to coordinate media and moderate stakeholders’ perceptions of the business. Align internal decisions and objectives made by different business units, as one assumption of another business unit can cause reputational damage when that goal is not met. 

### Sensitivity Impact
The aforementioned risks have varying sensitivities to Rarita’s overall ‘competitiveness’. Changes in interest rates and inflation will have a limited impact on the team’s success within the tournament, mainly affecting the initial stages of player salaries. Competition fines may have a moderate impact, affecting both the budget of the Rarita’s team, as well as influencing individual player selection to the team if the tournament inhibits players that receive too many fines. Retention rate similarly has a moderate impact, as if ‘competitive’ players decided to not play for Rarita in the subsequent tournament year, the overall team’s competitiveness may diminish. Lastly, reputational risk has a large influence on the team’s success as it may place pressure on the overall team’s motivation to succeed in the tournament.


# References
AP NEWS. 2022. World Cup winners can expect GDP boost to economy. [online] Available at: <https://apnews.com/article/soccer-sports-international-soccer-economy-world-cup-a9287f7aee7f2b7fbd35cf5a36b6168d> [Accessed 28 March 2022].

Eccles, R., Newquist, S. and Schatz, R., 2007. Reputation and Its Risks. [online] Harvard Business Review. Available at: <https://hbr.org/2007/02/reputation-and-its-risks> [Accessed 21 March 2022].

Frontiers. 2020. Healthcare Expenditure and Economic Performance: Insights From the United States Data. [online] Available at: <https://www.frontiersin.org/articles/10.3389/fpubh.2020.00156/full> [Accessed 28 March 2022].

theOECD. 2022. Household accounts - Household savings - OECD Data. [online] Available at: <https://data.oecd.org/hha/household-savings.htm> [Accessed 28 March 2022].

WhoScored.com. 2022. Adama Traoré Football Statistics. [online] Available at: <https://www.whoscored.com/Players/140088/Show/Adama-Traor%C3%A9> [Accessed 22 March 2022]. 



