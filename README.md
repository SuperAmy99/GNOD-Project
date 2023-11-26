![spotify_logo](https://storage.googleapis.com/pr-newsroom-wp/1/2018/11/Spotify_Logo_RGB_Green.png)

# Song Recommender
## Description

The primary goal is to develop a song recommendation model, beginning with the exploration of new data sources for popular songs. Initial data collection involves using APIs or web scraping to gather information from a few hundred or thousand songs per source. Subsequently, the focus shifts to clustering songs based on similarities, ensuring that recommendations prioritize songs within the same cluster when a user inputs a song from a specific group.


## Project approach

### 1. Web Scraping: Create a list of top_200_songs and make a simple recommender

- Utilized web scraping to compile a list of the top 200 songs from popular charts such as [Popvortex](https://www.popvortex.com/music/charts/top-100-songs.php) and [Billboard](https://www.billboard.com/charts/hot-100/).

- Implemented a straightforward recommender system based on the hypothesis that users are likely to enjoy recommendations of currently popular songs. If the input song is among the top 200 in the playlist, the recommender suggests a random song from the same playlist.

- The approach capitalizes on the assumption that songs currently on the top charts reflect user preferences, providing a simple yet effective way to offer relevant song recommendations.
  
### 2. API wrappers: Create a spotify playlist with appx 12,000 songs

- Leveraged the Spotify Web API to extract song titles, artist information, and detailed audio features for approximately 12,000 songs.

- This data extraction serves as the groundwork for thorough analysis and the development of a robust song recommendation model.
  
### 3. Unsupervised Learning: K-means clustering

- Employed unsupervised learning through K-means clustering on the playlist data, utilizing both the elbow method and silhouette score to determine optimal cluster count.
- Identified that the optimal number of clusters for further analysis is 8, as indicated by the elbow method and silhouette score, providing a foundation for more nuanced exploration and user-centric song recommendations within distinct clusters.


### 4. Song recommender: 

- Verify if the user-entered song is in the PopVortex Hot 100.
  If yes, recommend another Hot 100 song.
  If the user-entered song is not in the Hot 100:

- Utilize the Spotify API to fetch the audio features of the input song.
  - Apply the clustering model to the Spotify audio features, obtaining a cluster number.

- Recommend a song from the same cluster as the user-entered song.

## Prototype: 
<img width="1205" alt="image" src="https://github.com/SuperAmy99/GNOD-Project/assets/124481767/f31ff218-2d43-4f9a-bf90-54179d57e29a">

<img width="1035" alt="image" src="https://github.com/SuperAmy99/GNOD-Project/assets/124481767/357e5764-c688-472d-80bc-a06463267ad8">


This streamlined pipeline ensures dynamic song recommendations based on whether the user's song is currently popular or belongs to a specific audio feature cluster.


## Libraries

*pandas*\
*numpy*\
*BeautifulSoup*\
*spotipy*\
*json*\
*sklearn*\
*matplotlib*


