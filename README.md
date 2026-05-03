**Machine Leaning Based Instagram Marketing Strategy**

**ABSTRACT**
Supervised and unsupervised learning models answer the question of what are the best actions to
take. However, action does not end at selection, especially for business strategies such as social media
marketing. Combining the identification of best actions and the evaluation of actions taken creates a robust
strategy that would improve results and withstand the continuous evolution of social media. Reinforcement
learning provides an approach for evaluation of actions taken, with the optimal action based on whether
exploitation of opportunity, exploration of opportunity or a combination of both would be advantageous.
The project considers the potential of reinforcement learning for strategy development on the opportunity
of marketing through influencers on Instagram and the action of selecting which influencer(s) to market
with on the platform. Both supervised and unsupervised learning will be conducted for comparison and
complimenting of the reinforcement learning in the strategy development.
**INTRODUCTION / BACKGROUND**
Social media has extensive usage, that has been steadily growing overtime. Although originally designed
for social interactions, social media has evolved into a useful tool for influencers, businesses and marketers
to access the large audience of social media users . However, optimal utilization of social media, in
order to get returns on investment for businesses and marketers remains a challenge, given the continuous
evolution of social media and technology. A robust approach is hence needed by businesses and marketers
to determine what action to take in order to better utilize the opportunity of marketing on social media.
**PROBLEM STATEMENT AND MOTIVATION**
The population of social media users create a large audience and consequently a potential market for
businesses. The social media market differs from the conventional market and hence businesses cannot
approach marketing using the conventional approaches . Although companies have had time to adapt
to the social media market, the continuous evolution of social media, social media users and technology
required a robust approach that can withstand the evolution. An optimal approach would be beneficial in
informing businesses how best to allocate social media marketing budget in terms of the who (influencers),
when (timing), what (content) of social media marketing. Instagram data from Kaggle, will form the main
data utilized to for the evaluation of social media marketing actions, with Instagram used as the case of
focus. Additionally, data on stock market performance for main brands across industries, consistent with
categories for which the posts on Instagram fall and the date on which the posts were published, will be
used to provide context on influence of social media on stock performance. The data sets will be used in
the reinforcement, unsupervised and supervised learning to create a strategy that addresses the problem.
**METHODOLOGY / PROPOSED APPROACH**
The system leverages market data, Instagram user behavior data, influencer categorization, predictive
machine learning, and reinforcement learning in a hybrid analytical framework to help marketers un￾derstand how to best strategise their campaigns on Instagram. Drawing on techniques used in hybrid
analytical systems of advanced AI, this project combines several analytical layers to develop a scalable,
interpretable and safe marketing strategy system.

Starting with a large-scale data collection, this model involves stock market data, influencer engagement
on Instagram, hashtag performance data, posting patterns, and user demographic data. Market data was
used to assess the market sectors and industries showing high levels of customer and investor activity,
while the Instagram data was used to understand the trends in user activity with hashtags, content and
timing of posts.
Initially, a rule-based analysis layer was applied to assess both sector and industry groups’ market
activity. Average daily volume was used as an indicator of consumer demand, which enabled the system
to select top-performing market sectors such as Technology and Communication Services. Key industries
within these selected sectors (Consumer Electronics, Internet Content and Semiconductors) were chosen
to drive the hashtag campaign. This process provided a meaningful strategic basis that ensured social
media campaigns were linked to industries with high real-world attention .
Concurrently, exploratory data analysis of Instagram was performed for audience engagement in terms of
posting time, hashtags, and media type. Engagement historical data was examined to establish differences
and variations in engagement patterns between posting times and media types (images, carousels, reels) in
the morning, afternoon, evening and night. This set the expectation for behavioural metrics and identified
the most likely high audience response combinations.
To drive more effective influencer engagement, unsupervised machine learning using clustering analysis
was used to group influencer assets such as engagement rate, hashtag compatibility, posting frequency, and
number of followers. High Value, Mid Tier and Low Priority influences were identified. The clustering
approach enabled the system to choose influencer partnerships not only based on size, but also based on
marketing strategy .
Follower-tier analysis also added to this analysis and allowed influencers to be grouped into Nano, Micro,
Macro, and Mega segments. Distribution analysis revealed that smaller influencers often showed better
engagement efficiency than larger influencers, thereby delivering further insights for business decision making on influencer marketing budget and campaign planning.
We added a supervised learning layer based on a RandomForestRegressor model to forecast the outcomes
of engagement. These included influencers’ cluster, media type, hashtag type, and post time. Through
feature importance analysis, it was observed that influencer cluster had the greatest impact on predicting
engagement, justifying the value of quality influencer content over individual content elements .
Secondly, analysis of the relationship between stock market movements and Instagram engagement
was done through Pearson correlation coefficients with major brands. This aspect gauged the correlation
between external financial activities and social media response, contributing another layer of adaptability
to the campaign.
The last component of this process was a decision-making strategy using reinforcement learning (RL).
This RL approach modeled hashtag, time, and media type combinations as strategy states, and estimated engagement as cost. The agent learned to optimally combine exploration of these strategies with exploitation
of strategies that performed well in the past. This allowed for iterative development of recommendations
for optimal times to post on Instagram.
The unified framework enhances explainability and performance, integrating predictive machine learning
with explainable business strategy. Other outputs such as predicted engagement rankings, feature importance, influencer value rankings, and Q-value strategy rankings are also provided, helping marketers to
test and finalise their strategies.

**RESULT SECTION**
A complex multi-model artificial intelligence system was successfully developed to produce an effective,
data-driven Instagram marketing optimization system that incorporated external and internal data sources
(stock market and Instagram user analytics), influencer behavior reports, supervised machine learning, and
reinforcement learning. The system proved the timeliness of aligning external financial intelligence with
internal social media data can enhance strategic campaign success, and increase marketing decision-making
accuracy.
The reinforcement learning model was the final layer of strategic optimization that identified the
best combination of posting, in terms of hashtag, posting time and media type. The combination of
MadeByGoogle as a hashtag, using imagery content in the format of a reel and posting in the morning
yielded the highest expected engagement (as predicted to be 179 interactions), the highest expected Q
value (model evaluation variable), and the highest mean Q-value across the combinations. This suggests
better long-term performance. The AppleEvent2025 in morning with carousels and GalaxyS25 in morning
with images were other high performing combinations, reaffirming the smartness of technology-related
campaigns in line with the latest market trends .
The stock market and sector layer supported the value of leveraging external market insights for
campaigns. The Technology and Communication Services sectors always showcased the highest market
sentiments while Consumer Electronics was the strongest industry. This market intelligence was applied
for selecting campaign hashtags and positioning social media activities with trend awareness.
Social media engagement analysis demonstrated that while timing impacts Instagram campaign per￾formance, media and content alignment and hashtag relevance are also key factors. The analysis of time
of day showed that peak engagement generally occurred in the early and late hours of the day, but
that campaign success continued to depend on multi-variable timings of regions, content, and influencer
strategies. These results highlight the need for multi variable management over independent posting time
tactics for Instagram optimization .
Clustering and follower tier profiling of influencers produced significant business intelligence via
showing that high value influencers have a greater impact than follower size (quantity). High Value
influencers consistently scored higher than Mid Tier and Low Priority influencers in terms of engagement,
relevant hashtags and content frequency. In addition, Nano and Micro influencers often created higher

Engagement Efficiency than Mega influencers, suggesting that smaller influencers are often more valuable
for marketing strategies due to niche target audience trust and authenticity.
The RandomForestRegressor model extensively supported these insights as influencer cluster is the most
influential variable driving Instagram engagement. Influencer cluster was significantly more important for
prediction than the type of media, hashtag and time of posting. This validates the role of influencer
targeting as a key strategic component to social media marketing success.
The correlation with the stock market added an extra dynamic dimension, as correlation between
market and Instagram for brands varies. Apple was positively correlated, Google negatively correlated, and
Samsung slightly correlated. These differences imply campaign timing and development can be further
enhanced by leveraging the market behavior of the financial market.
In conclusion, it achieved its aim of producing an interpretable, scalable AI-based Instagram marketing
recommendation system that can continuously refine campaign strategies to take into account changes in
market, audience and influential factors. The fusion of explainable analytical approaches with adaptive
reinforcement learning enabled an influential strategic system for improving the return on investment in
social media marketing. 
