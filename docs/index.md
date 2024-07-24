# ME204 (2024) | Ben

## About me: 
- I am a Data Science and Economics Student from Northwestern University and I created this project as part of the LSE Summer School ME204 course (2024). I have always loved number and sports, and my eventaul career will be in sports data analysis where I can use my two passions. 

## Data 
- Source: Spotify API (Spotipy- python's package for Spotify API) 
    - [https://developer.spotify.com/documentation/web-api]

- I chose this datasource because I enjoy listening to music and always wondered what the categories of featured playlists were in the Spotify algorithm. This project attempts to investgate these categories along with the number of followers the playlsit has. 

- The most challenging part of collecting the data was the runtime. The Spotify API has a limit to how many requests a user can do, and I reached that limit multiple times. According to the documentation, the limit is described in 30 seconds intervals. Spotify does not list the actual number of requests allowed at a time. 

### Collecting the Data
- I collected the data through the Spotify API in predefined functions named `spotify.featured_playlist()`- which obtains the top 20 playlists in Spotify at the current time. Other functions include `spotify.artist()`- which obtains the info of the artist. 
- Data was collected by looking at the featured playlists, then obtaining the artists of all tracks in the playlist, and finding the categories of those artists. After obtaining all data, it was concatenated in a list. 


Key Findings: What are the main insights you gained from your data? What are the most interesting things you found? Something like “Once I cleaned up the data by doing X, Y and Z, I found that the price of bread in the UK has increased by 20% in the last 5 years while the price of milk has remained stable, as shown in the plot below” would be a good example.

Future: What would you do next if you had more time? What other questions could you ask of this data? What other data sources could you use to complement this data?