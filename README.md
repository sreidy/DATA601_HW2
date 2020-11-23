# UMBC DATA 601 HW2: Spotify Web API!!

This project is an explotation of the [Spotify Web API](https://developer.spotify.com/documentation/web-api/). I pull a dataset of Spotify tracks, clean and process that data, and create various visualiztions of both continious and catigorical data.  

![spotify_img](https://developer.spotify.com/assets/WebAPI_intro.png)

# Introduction

In this project, we take a look at [Spotify Track Feature Data](https://developer.spotify.com/documentation/web-api/reference/tracks/get-audio-features/).  

Scenario: As we will try to predict a counties median house price, we suppose we are working for CA housing department. As a result of this project we will give them suggested median housing prices based on a counties demographic information.

Task Example: What type of music is the most dancable, or the most lyrically dense? How could this data be used to build a genre classifier for futrue projects.

# Goals

This assingment has both two types of goals:

- Learn how to implment the Spotify Web Api, by building a script that can query n number of playlists given a catigory, and save that track data to disk. 
- Use EDA concepts, including but not limited to, distributions, data summaries, and visualizations to explore the differences between the tracks in each spotify category.

# Motivation & Background

Music is deeply personal and it is often hard to describe what about a certain genre of music combless us to listen. Why am I more likely to listen to one genre over another when I am feeling a certain mood? The Spotify Web API gives us insights into many different descriptions of tracks, and with this data we can explore what characteristics define a given genre. This Process of Spotify EDA would provide helpful insight into building a genre classifier of a playlist generating algorithm that builds a playlist based on a user's mood.  

Similar projects and tutorials references on the Spotify Web API and python data science
	+ https://medium.com/@maxtingle/getting-started-with-spotifys-api-spotipy-197c3dc6353b Shows how to implment the Spotipy python package to acess the Spotify Web API and save the results to a pandas data frame.
	+ https://www.kaggle.com/nicapotato/top-spotify-tracks-2019-eda/execution An example of EDA on spotify feature data 


# Table of Contents

- Data: Includes data
	+ spotify_df.csv : a .csv of the dataset 
	+ spotify_df.pkl : a python pickle saved spotify dataframe element 
	+ spotify_dict.pkl : a pickel of the  dictionary of playlists
- Notebooks
	+ getSpotifyData.ipynb : Quering, cleaning, and saving the data from the Spotify Web API 
	+ spotifyTechnicalNotebook.ipynb : A high level overview and EDA of the dataset 
	
# Software Requirements & Usage

- Packages Used: 
	+ [Spotipy](https://spotipy.readthedocs.io/en/latest/#): A Python library for the [Spotify Web API](https://developer.spotify.com/documentation/web-api/)
	+ [getpass](https://pymotw.com/2/getpass/#module-getpass): A Python library to hide spotify web API credentials 
	+ [pickel](https://docs.python.org/3/library/pickle.html): used to save the spotify dataframe to disk
	+ [pandas](https://pandas.pydata.org/docs/)
	+ [matplotlib](https://matplotlib.org/3.3.3/contents.html)
	+ [seaborn](https://seaborn.pydata.org/)

# Dataset

If you want a local copy of the data, please go to `Notebooks` folder and run getSpotifyData.ipynb notebook. You will need a spotify account and have a spotify client ID and client secret. To find this look at your [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/applications) The dataset contained in this repo was pulled on Thu 19 Nov 2020 05∶13∶29 PM EST. Running this code will create a potentially different dataset of tracks.

I collected a dataset of 9767 rows and 18 columns. Each row is a sporitfy track withe the following metadata and Spotify audio feature objects. 
	+ track_id : a spotify primary key; unique for each track
	+ artist: name of artist
	+ album: name of album
	+ trackName: title of track
	+ acousticness: A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 1.0 represents high confidence the track is acoustic.
	+ danceability: Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable. 
	+ duration_ms: The duration of the track in milliseconds.
	+ energy: a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. 
	+ instrumentalness: Predicts whether a track contains no vocals. “Ooh” and “aah” sounds are treated as instrumental in this context.
	+key: The estimated overall key of the track. Integers map to pitches using standard [Pitch Class notation](https://en.wikipedia.org/wiki/Pitch_class) 
	+liveness: Detects the presence of an audience in the recording.
	+loudness: The overall loudness of a track in decibels (dB). 
	+mode: indicates the modality (major or minor) of a track, the type of scale from which its melodic content is derived. Major is represented by 1 and minor is 0.
	+speechiness: Speechiness detects the presence of spoken words in a track.
	+tempo: BPM of track
	+time_signature: An estimated overall time signature of a track. 
	+valence: A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. 
	+category_id: The Spotify Category ID of the track 

The final data set contains 8921 unique tracks and 5207 unique artists across 12 differnt spotify catigories; Rock, Pop, Country, Hip Hop, EDM Dance, Indie Alt, R&B, Classical, Jazz, Punk, Kpop, and Metal. 

[For more information please check](https://developer.spotify.com/documentation/web-api/reference/)
