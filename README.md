### Sams-Baseball-Zone
# Context-Neutral Linear Weights (wOP+) vs. Environmentally Adjusted Metrics (wRC+)

# Research Question: Why do modern baseball front offices heavily favor weighted metrics influenced by environmental variables (like wRC+) versus raw, context-neutral linear data (Weighted Offensive Production (my stat) (wOP+)? What are the strategic pros and cons of each, and how can a hybrid approach improve talent evaluation and roster construction?

Disclaimer: I used Python to code this project, and I used the aide of Gemini with coding outlines and unknown syntax. 

wRC+ is a widely known and analyzed stat in Major League front offices that is used to help determine a players worth and offensive productiveness. One of its main ingredients that makes it stand out from the rest, is its variable weights that's inside its equation, including ball park factors, and LR/BA (league run average/ plate appearance is roughly 0.11 to 0.12 per PA, which means a team roughly scores 1 run every 8 or 9 plate appearances.). But what would happen, if someone created a statistic that used context-neutral linear weights (like run expectancy per raw stat), and compared that stat to wRC+, what would be the outcome? Well, that's exactly what I set out to do, by creating Weighted Offensive Production (wOP+)! If you want a full breakdown of this project, I will link the pdf here: ![Full wOP+ vs. wRC+ Analysis](** . 

For the weighting system of my stat, I pulled from FanGraphs "Guts!" section, and used the run expectancy weights for these stats: BB, HBP, 1B, 2B, 3B, HR, SB, and CS. I then averaged players' scores on the same scale as wRC+ uses, making a "100" score the average player's score. I kept the minimum plate appearances to 500, to keep things consistent. I wanted to analyze everyday players for this analysis.  

Here is my first pull of data from my github repository showing the top 20 Players for wOP+ from 2026: 

![Top 20 wOP Players](Top%2020%20wOP%20players.PNG)

And here is the list of the top 20 players when looking at wRC+ (minimum 500 PA's):

![Top 20 wRC Players](top%2020%20wRC%20players.PNG)

As you can see, these lists have a lot of players in common, 17 in fact are on both lists, that's an 85% alignment between the two, which shows on a base level, that using both of these stats as legitimate assessments for talent, are viable options to use. However, there are some outliers involved, and I am going to be analyzing and breaking down 3 of them here, to try and look deeper into the data, to see why one was on one of the lists, but not the other. But before that, I wanted to compare the matching 17 players, and see if I found any interesting discoveries.

Below, is a Delta chart that I created, showing the difference in wRC+, and wOP+. The biggest outlier here is Yordan Alvarez. His delta is +49, the biggest out of the 17 players. The rest of them are all in the +20-35 range, but this tells a story. My wOP+ strictly weighs players performances on linear weights, based solely on walks, singles, doubles, triples, home runs, stolen bases, and caught stealing attempts. The gap between the two, is how wRC+ inputs its environmental factors, how it weighs ball park metrics, whether a hitter is hitting well in a pitcher’s park or vice versa, and the League Runs per Plate Appearance for that given season. Those factors show in the biggest of deltas (Yordan Alvarez), and it is a good contrast between the more concise, conservative wOP+, and the more heavily weighted and always changing wRC+. 

# The Outliers

Here is where the interesting diversions happen when looking at the outlier players. For each one, I am going to analyze their wOP+ and wRC+ difference, make a hypothesis for the why there's a difference, and I will look at a few determining factors to see why they are distinct from one another, and to see if there is some underlying stats that are getting over looked: The ball park they play in, the League Runs per AB for 2026, and their Statcast numbers (exit velocity, average launch angle, hard hit ball rate, etc.). First up, Kyle Schwarber. 

![Delta Chart for wRC+ - wOP+](Delta%20between%20wRC%20and%20wOP.PNG)

# Kyle Schwarber
wOP+: 113+

wRC+: 130+

Hypothesis: Kyle plays in Philadelphia, one of the more hitter friendly parks, especially for pull side lefties like himself, he fits perfectly there with his swing. I think the ball park factor is a bigger drawback for him in this scenario when looking at his wRC+. 

Analysis: Kyle barely missed out on the wRC+ top 20, ranking 22nd. I think his wRC+ rating and wOP+ ratings are valid. The reason why he did not break into the top 20 is mainly due to one factor: where his home team plays. He is a huge pull side hitter, and Philadelphia favors lefty pull hitters, as you can see for his spray chart:

![Schwarber Spray Chart](Schwarber%20Spray%20Chart.PNG)

![Schwarber Percentiles](Schwarber%20Percentiles.PNG)

It’s a decently short porch, and regardless where he plays, he ranks in the 99th Percent Value for Batting Run Value on Baseball Savant, Kyle is property rated in both stats. A good comparison to make for Kyle is Junior Caminero. Junior ranks 12th in wOP+, but ranks 8th in wRC+. The main reason why? Tropicana Field is a much harder place to be a good hitter than Citizens Bank Park is.

# Max Muncy (the anomaly of the outliers )
wOP+: 111

wRC+: 129

Hypothesis: He is 18th in wOP+, but 28th in wRC+ with a 129+. It’s interesting, he is 2% more average than Kyle Schwarber is when looking at wOP+ (2 points less than Kyle), but he is only 1% more average than Kyle when looking at wRC+. What I think is going on here, is that Max plays in a slightly harder hitter environment in LA, which is why wRC+ is giving him a boost in points, but is raw stats are slightly worse than Kyle’s, hence the lower wOP+. Let’s look deeper:

Analysis: There is definitely something interesting going on with Max’s case here when comparing it to Kyle’s stats. So yes, Max DOES play in a harder hitting environment in LA, he is a pull hitter, take a look at his spray chart:

![Max Muncy Spray Chart](Max%20Muncy%20Spray%20Chart.PNG)

That right field fence is on average 25-30ft farther than Citizens Bank Park. But here is something very very interesting. When looking at Max’s Baseball Savant, his metrics do not pop off like Kyle’s do:

![Max Muncy Percentiles](Max%20Muncy%20Percentiles.PNG)

His batting run value only sits at 87, which is still super great. But his avg exit velo is in the 64th percentile, and Kyle’s is in the 93rd percentile. Almost every major metric here, like xSLG, Barrel %, Sweet Spot%, etc., are all substantially lower than Kyle Schwarber’s, but Kyle only has a 1% buffer in wRC+ than Max does? I think this is a great example of how wRC+ can be a flawed metric when not taking into account other stats like Baseball Savant presents. Again, Kyle plays at a more hitter friendly park, but you can’t argue with statcast data, Kyle just swings the bat better than Max does, but is only granted a 1% buffer above him. That being said, using baseball savant also hinders wOP+’s validity too, even though there is a 3% buffer between the players, using savant gives a full picture of who really is the better hitter. 

# Riley Greene
wOP+: 110

wRC+: 136

Hypothesis: Riley barely missed out in the top 20 for wOP+, sitting at 21st, right behind Seiya Suzuki. But he is ranked 14th in wRC+ with 136, big jump for him. He is 6% better than Kyle Schwarber, which makes me think: Comerica park has to have a huge play in his wRC+, super pitcher friendly place. Let’s look into the data:

Analysis: As assumed, Riley is a great, great hitter. He always makes good contact, he gets on base a lot, and that’s attributed not only to his high number of hits, but he is in the 86th percentile in walks, which is a key stat used in both statistics. He hits the ball around, per his spray chart:

![Riley Greene Spray Chart](Riley%20Greene%20Spray%20Chart.PNG)

He has only 21 home runs, which could be attributed to the bigger field he plays at. But I also think this is a good example of wRC+ adjusting for park factors. Take a look at his statcast numbers:

![Riley Greene Percentiles](Riley%20Greene%20Percentiles.PNG)

Riley has very good bat-to-ball skills, a little less than Kyle does, but much more than Max does on average. And with the adjustment with the park factor, it goes to show that wRC+ for Riley Greene does really show how good of a hitter he really is, and Baseball Savant backs up that claim. And his wOP+ is still really solid, 10% above the average hitter. I think this, out of the 3 players shown, is the best analysis for why wRC+ is highly rated statistic, because his actually in game stats, how he hits the ball, how he actually plays on the field, matches the up tick in his wRC+ score, unlike Muncy's. 

# Conclusion

Going back to my research question, I think stats like wOP+ that are context-neutral, and just take a players raw stats, can still be a very useful way to assess a player’s ability, but it’s not without it’s drawbacks, like inflating players who play in easy ball parks for example. On the flipside, wRC+ is a heavily used statistic in today’s game, and it has its perks, but there are some players who fall through the cracks, like Max Muncy for example. His park factor benefited him greatly, but taking a look at his statcast metrics, and using wRC+ to judge him solely, would be a mistake in my eyes.

I also think it is important to note, that yes, these outlier players had reasons to not be in the other top 20 list, but all of them are elite players. For the most part, if one of these outliers were not in the top 20 of one of the stats, they were definitely in the top 40 of it. What I am saying is, I am analyzing marginal outliers in this data, just for context. But the importance of breaking each individual player down, and creating a profile for them, brought their weighted stats and statcast data to life, and it allows a scout, a front office executive, and managers to build a more sustainable way of analyzing player talent. 

Overall, I believe that front offices should not just look at one, or even two stats as their main grading scale when analyzing players (and the good front offices do not do this), but they should look at all players stats, and most importantly, while the data and stats can prove a players productiveness, the human touch and analysis of a player on the field playing the game, is the most crucial key to the puzzle. Because baseball, even though it’s very data driven now, at its core, is a human experience, and it is played by, watched by, and loved by humans. 






