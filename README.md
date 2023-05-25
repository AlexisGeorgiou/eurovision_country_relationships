# Eurovision countries' relationships

You can see the visualization here: https://alexisgeorgiou.github.io/eurovision_country_relationships/

# Summary
In the visualization, you can see how biased is each country on their vote for other countries and the other way around.
So in simple words, you can who "likes" each country and which country "likes" who.
You can click each country to see the information, and there are also two buttons that you can choose which relationship you want to see "likes" or "liked by".

# Basic implementation:
I used the data from https://data.world/datagraver/eurovision-song-contest-scores-1975-2019/workspace/file?filename=eurovision_song_contest_1957_2023.xlsx
Had to preproccess it a bit, and then modified the data by multiple doing multiple queries and calculated a score based on each unique pair.
Then used a javascript module to visualize the map. The js code is a little messy but it is better than any other option in python (folium, geopandas etc).
The relationship is a unique pair of two countries (X->Y), the order matters since "X votes for Y". We can calculate how strong this relationship is by the following formula. We get all the events that this pair occured, and we add on the score the difference between the points given and the average points Y country received (this is the total Y points the country received on the specific event divided by the amount of voting countries). Then we just divide this sum by the number of events this pair was found.

# More details:
The score is based on televoting points only, I can add jury in the furure too but I was more interested in the televoting. Televoting is quite old in eurovision but it was only publicly shared since 2016. Before 2016 the televoting points were announced averaged with the jury votes which makes it noisy for my purpose. 

# Interesting stuff, future work
Using this map we can see how each country's population is more keened to vote for "friendly" nations. I had also made other interesting visualation, such as the stronger relationships between countries in eurovision. An interesting application is to use the relationships to come up with a score to balance semi-finals sub groups. Since semi-finals are only based on televoting (since 2023), we can come up with two sub-groups that will have as little deviation as possible between their members. This would make the competition more fair, at least for the semi-final stages.
I will add more filters in the future for Jury and for Jury and Tele together which could allow me to add older events too.
