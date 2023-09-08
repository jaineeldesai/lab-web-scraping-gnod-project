![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Lab | Web Scraping, API Wraping and Kmeans Clustering (GNOD Project)

#### Business goal:

- Check the `case_study_gnod.md` file.
- Make sure you've understood the big picture of your project:

  - the goal of the company (`Gnod`),
  - their current product (`Gnoosic`),
  - their strategy, and
  - how your project fits into this context.

  Re-read the business case and the e-mail from the CTO.

#### Instructions

1. Scraping popular songs

Your product will take a song as an input from the user and will output another song (the recommendation). In most cases, the recommended song will have to be similar to the inputed song, but the CTO thinks that if the song is on the top charts at the moment, the user will also enjoy a recommendation of another song that is popular at the moment.

You have to find data on the internet about currently popular songs. Popvortex maintains a weekly Top 100 of "hot" songs here: [http://www.popvortex.com/music/charts/top-100-songs.php](http://www.popvortex.com/music/charts/top-100-songs.php).

It's a good place to start! Scrape the current top 100 songs and their respective artists, and put the information into a pandas dataframe.

2. API wrappers - Create your collection of songs & audio features

To move forward with the project, you need to create a collection of songs with their audio features - as large as possible!

These are the songs that we will cluster. And, later, when the user inputs a song, we will find the cluster to which the song belongs and recommend a song from the same cluster. The more songs you have, the more accurate and diverse recommendations you'll be able to give. Although... you might want to make sure the collected songs are "curated" in a certain way. Try to find playlists of songs that are diverse, but also that meet certain standards.

3. Unsupervised learning

Clustering the songs will allow the recommendation system to limit the scope of the recommendations to only songs that belong to the same cluster - songs with similar audio features.

The activities you did with the Spotify API and the PopVortex web scraping will allow you to create a pipeline such that when the user enters a song, you:

  1. Check whether or not the input song is in the PopVortex Hot 100.
  2. Recommend another Hot 100 song
  3. If it is NOT in the hot 100, then collect the audio features from the Spotify API for the input song.
  4. You want to send the Spotify audio features of the submitted song to the clustering model, which should return a cluster number.
  5. Then you recommend a song from the same cluster number.
