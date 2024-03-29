# Music-Mood-Visualizer-using-Pipelines

Full-Text PDF Available!: https://www.researchgate.net/publication/351412160_Music_Mood_Visualizer_using_Pipelines

Introduction:
1. Music is a powerful tool, it is a reflection of our current mood and overall personality. Emotions and moods can be expressed by music – for example, when one is anxious or stressed, a calming song could help them ease their nerves. If one is sad, listening to a happy or uplifting song can liven up one’s mood.
2. The classification of music however, can be a difficult task since emotional reactions towards songs can be quite subjective and differ widely between listeners for a given song. A considerable amount of the present day song organization system is based on an artist’s overall genre, rather than on the feeling generated by a song.
3. Attempting to categorize music through machine learning techniques is challenging, but can potentially help to minimize these discrepancies between listeners and the algorithmic suggestions provided by music services. Hence, we have tried to figure out how one can develop an ML model using various python libraries such as spotipy, sklearn, seaborn, matplotlib, Keras and TensorFlow. These libraries can help us identify under which vibe categories certain songs fall under and how this data correlates with each other.


Overview:
Let’s take a look at some of our dataset features [5][7]:
1. Acousticness: A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 1.0 represents high confidence the track is acoustic.
2. Danceability: This describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable.
3. Energy: This is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. For example, death metal has high energy, while a Bach prelude scores low on the scale. Perceptual features contributing to this attribute include dynamic range, perceived loudness, timbre, onset rate, and general entropy.
4. Instrumentalness: Predicts whether a track contains no vocals. “Ooh” and “aah” sounds are treated as instrumental in this context. Rap or spoken word tracks are clearly “vocal”. The closer the instrumentalness value is to 1.0, the greater likelihood the track contains no vocal content. Values above 0.5 are intended to represent instrumental tracks, but confidence is higher as the value approaches 1.0.
5. Liveness: Detects the presence of an audience in the recording. Higher liveness values represent an increased probability that the track was performed live. A value above 0.8 provides a strong likelihood that the track is live.
6. Loudness: The overall loudness of a track in decibels (dB). Loudness values are averaged across the entire track and are useful for comparing the relative loudness of tracks. Loudness is the quality of a sound that is the primary psychological correlate of physical strength (amplitude). Values typically range between -60 and 0 db.
7. Speechiness: This detects the presence of spoken words in a track. The more exclusively speech-like the recording (e.g. talk show, audiobook, poetry), the closer to 1.0 the attribute value. Values above 0.66 describe tracks that are probably made entirely of spoken words. Values between 0.33 and 0.66 describe tracks that may contain both music and speech, either in sections or layered, including such cases as rap music. Values below 0.33 most likely represent music and other non-speech-like tracks.
8. Valence: A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry).
9. Tempo: The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, the tempo is the speed or pace of a given piece and derives directly from the average beat duration.

Classification problems use labeled data [6]. Hence, we created 4 categories to label the tracks, these categories are “Energetic”, ”Calm”, “Happy” and “Sad”.
 
 
[6] We chose features such as Length, Danceability, Acousticness, Energy, Instrumentalness, Liveness, Valence, Loudness, Speechiness and Tempo because they are more likely to have higher influence on the classification process.
 
While scraping data from the public Spotify API, we couldn’t fit the model on the training data and can’t say that the model will work accurately for the playlist data. For this, we must assure that our model develops the correct patterns from the data, and it is not processing too much noise. Hence, we use the cross-validation technique in which we train our model using the subset of the compiled dataset and then evaluate using the complementary portion.
The three steps involved in cross-validation are as follows:
1.	Reserve some portion of the subset.
2.	Using the rest of the dataset, train the model.
3.	Test the model using a reserved portion of the compiled dataset.
For the purposes of this project, we use fold cross validation in which we split the data-set into k number of subsets (known as folds) then we perform training on all the subsets but leave one (k-1) subset for the evaluation of the trained model.
 In this method, we iterate k times with a different subset reserved for testing purposes each time.
The error in measuring values is measured by the root mean square error (RMSE) is a method of measuring the difference between values predicted by a model and their actual values.
Based on a rule of thumb, it can be said that RMSE values between 0.2 and 0.5 shows that the model can relatively predict the data (relatively) accurately [9][10][14].

References:

[1] Comparison of Logistic Regression and Linear Regression in Modeling Percentage Data by Lihui Zhao, Yuhuan Chen and Donald W. Schaffner (2001), https://aem.asm.org/content/aem/67/5/2129.full.pdf

[2] How Many Trees in a Random Forest? by Thais Mayumi Oshiro, Pedro Santoro Perez, and Jose Augusto Baranauskas (2012), https://www.researchgate.net/profile/Jose_Baranauskas/publication/230766603_How_Many_Trees_in_a_Random_Forest/links/0912f5040fb35357a1000000/How-Many-Trees-in-a-Random-Forest.pdf

[3] A Random Forest Guided Tour by Gerard Biau Erwan Scornet (2015), https://arxiv.org/pdf/1511.05741.pdf

[4] To Tune or Not to Tune the Number of Trees in Random Forest by Anne-Laure Boulesteix and Philipp Probst (2018), https://www.jmlr.org/papers/volume18/17-269/17-269.pdf

[5] Understanding User Behavior in Spotify by Boxun Zhang, Gunnar Kreitz, Marcus Isaksson and Javier Ubillos (2013), http://www.hugoribeiro.com.br/biblioteca-digital/Zhung-Understanding_User_Behavior_in_Spotify.pdf

[6] Music Mood Classification by Michael Nuzzolo (2015) https://sites.tufts.edu/eeseniordesignhandbook/2015/music-mood-classification/

[7] Understanding User-Curated Playlists on Spotify: A Machine Learning Approach by Martin Pichl, University of Innsbruck, Innsbruck, Austria Eva Zangerle, University of Innsbruck, Innsbruck, Austria Günther Specht, University of Innsbruck, Innsbruck, Austria (2017), https://evazangerle.at/publication/ijmdem-17/ijmdem-17.pdf

[8] A Generalized k-nearest neighbour rule by E. A. Patrick and F. P. Fishcher, III School of Electrical Engineering, Purdue University, Lafayette, Indiana 47907 (1970), https://www.sciencedirect.com/science/article/pii/S0019995870900811

[9] Evaluation Of Musical Features For Emotion Classification by Yading Song, Simon Dixon, Marcus Pearce Centre for Digital Music, Queen Mary University of London (2012), https://archives.ismir.net/ismir2012/paper/000523.pdf

[10] Automatic Music Emotion Classification Using Artificial Neural Network Based on Vocal and Instrumental Sound Timbre by Mudiana Binti Mokhsin and Nurlaila Binti Rosli (2014), https://books.google.co.in/books?hl=en&lr=&id=oN3YBAAAQBAJ&oi=fnd&pg=PA3&dq=music+emotion+classification&ots=7J9ty2torr&sig=uJjfGx3Z1WpbmfO1AO6Ok2H2EXA&redir_esc=y#v=onepage&q=music%20emotion%20classification&f=false

[11] Decision Trees by Lior Rokach and Oded Maimon (2003), https://www.ise.bgu.ac.il/faculty/liorr/hbchap9.pdf

[12] Simplifying Decision Trees by J. R. Quinlan (1986), https://dspace.mit.edu/bitstream/handle/1721.1/6453/aim-930.pdf?sequence=2

[13] A Decision Tree Classifier For Large Datasets (1998), https://www.aaai.org/Papers/KDD/1998/KDD98-001.pdf

[14] Multilabel Classification of Music into Emotions by Konstatinos Trohidis, Grigoris Tsoumakas, George Kalliris, Ioannis Vlahavas (2008), https://books.google.co.in/books?hl=en&lr=&id=OHp3sRnZD-oC&oi=fnd&pg=PA325&dq=music+emotion+classification&ots=oGJRtHiA71&sig=IpNJdbkuM-AE1Muvw4eU_DORmrQ&redir_esc=y#v=onepage&q=music%20emotion%20classification&f=false

[15] K-Means Clustering Tutorial by Kardi Teknomo (2007), https://people.revoledu.com/kardi/tutorial/kMean/





