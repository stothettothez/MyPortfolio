# Beethoven's ninth

Beethoven's ninth, a piece commonly known, can have a lot of different meanings for different persons. Some people only find the music soothing and beautiful, while other people use it as an identifier, since it's the anthem of the European Union. Considering this year has brought us Brexit and realising that Beethoven was born 250 years ago this year, gave me a good reason to investigate this masterpiece of a symphony.
On Spotify there are countless different versions of this piece. All performed by different conductors with different orchestras. I wanna know what the differences are between these versions. Performing a classical piece like this one doesn't come with a lot of freedom in interpretation. I wonder whether Spotify statistics are able to identify the small differences between versions. 
To investigate this i implemented the data of 40 different versions in R. The features i used are danceability, energy, loudness and tempo. Danceability might seem strange in the context of a symphony, however in my research i use it not to measure how 'danceable' a track actually is, but to add a variable to my comparison to get a better view of the symphony as a whole. I think the way Spotify constructs the danceability feature and especialy the different elements they look at are interesting enough to use in my research. The next feature is energy. With this feature i try to measure the activity and intensity between the different versions. I'm also gonna measure the loudness of the different versions. Loudness is less of an identifier in my research but it could make differences or similarities between the different versions more conclusive. The last feature i used is tempo. This feature analyses the song by bpm. Spotify takes the mean of the tempo throughout the song. This could result in slightly incorrect data, since the symphony contains a lot of tempo changes. Nevertheless i think it can be very useful in drawing a comparison between the different versions. 
The code i used to analyse the different versions is this:

london_symphony_danceability <- london_symphony %>% summarize(M_danceability = mean(danceability), SD_danceability = sd(danceability))

london_symphony_energy <- london_symphony %>% summarize(M_energy = mean(energy), SD_energy = sd(energy))

london_symphony_loudness <- london_symphony %>% summarize(M_loudness = mean(loudness), SD_loudness = sd(loudness))

london_symphony_tempo <- london_symphony %>% summarize(M_tempo = mean(tempo), SD_valence = sd(tempo))


This string of codes is the one i used for every one of the versions of the symphony. Then i checked the different means and standard deviations of the variables to look for any interesting differences/similarities. 
The means of the dancibility of the different versions were quite close to each other. Almost all of them were concertrated between 0,20 and 0,29. Only one of the versions of the symphony resulted in a mean of 0,34 with a standard deviation of 0,05. This is the version performed by Cyprien Katsaris. A French pianist and composer. 
The means of the energy variable were also quite centered, between 0,10 and 0,26. Only one of the means had the extreme value of 0,39 with a standard deviation of 0,13. This version is the version by Arturo Toscanini, an Italian conductor. 
The last variable, loudness, is a more divided one. With standard deviations starting at 3,65 and a maximum of 6,44 there is no clear thing to conclude from this data. Also the means are strongly divided, ranging from -17,4 to -26,4. 
In conclusion there is nothing significant to say about one of the versions. I can hear the low mean of the dancibility in the version of Cyprien Katsaris. This is a more rhytmic and more uptempo version of the symphony. The more energetic version by Toscanini is a little bit harder for me to hear. It's only a bit more uptempo than the other versions. 
