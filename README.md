![Project logo](https://imgur.com/HpMr0vs.png)
# Eurovision voting relationships

You can see the visualization here: https://alexisgeorgiou.github.io/eurovision_country_relationships/<br>

# Summary
In the visualization, you can see how biased is each country on their vote for other countries and the other way around.<br>
So in simple words, you can who "likes" each country and which country "likes" who.<br>
You can click each country to see the information, and there are also two buttons that you can choose which relationship you want to see "likes" or "liked by".<br>

# Basic implementation:
I used the data of [Stephan Okhuijsen in data.world](https://data.world/datagraver/eurovision-song-contest-scores-1975-2019/workspace/file?filename=eurovision_song_contest_1957_2023.xlsx), it contains every vote for 1957 to 2023 contests.<br>
I had to preproccess, and modify the data by doing multiple queries and calculate a score based on each unique pair.<br>
Then used a javascript module (amcharts) to visualize the map. The js code is a little messy but the result is better than any other option in python (folium, geopandas etc).<br>
The relationship is a unique pair of two countries (X->Y), the order matters since "X votes for Y". We can calculate how strong this relationship is by the following formula. We get all the events that this pair occured, and we add on the score the difference between the points given and the average points Y country received (this is the total Y points the country received on the specific event divided by the amount of voting countries). Then we just divide this sum by the number of events this pair was found.

# More details:
The score is based on televoting points only, I can add jury in the furure too but I was more interested in the televoting. Televoting is quite old in eurovision but it was only publicly shared since 2016. Before 2016 the televoting points were announced averaged with the jury votes which makes it noisy for my purpose. 

# Interesting stuff, future work, how could this be useful?
Using this map we can see how each country's population is more keened to vote for "friendly" nations. I had also made other interesting visualation, such as the stronger relationships between countries in eurovision. An interesting application is to use the relationships to come up with a score to balance semi-finals sub groups. Since semi-finals are only based on televoting (since 2023), we can come up with two balanced sub-groups that will have as little deviation as possible between their members. This would make the competition more fair, at least for the semi-final stages.
I will add more filters in the future for Jury and for Jury and Tele together which could allow me to add older events too.

## Future work technical stuff
I would like to improve the UI a bit (add legends/labels, use colors in buttons, color the selected country), make the buttons more function, maybe add some flags, change the coordinates of Australia to be closer in Europe and make a Rest of the world country. Add Jury vote filter. Come up with more visualizations.

<img align='center' src="https://imgur.com/2c7HPXE.png" width=50% height=50%>
