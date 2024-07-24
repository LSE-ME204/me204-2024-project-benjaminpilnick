
# Packages Requried
- __!pip install pandas spotipy tqdm__

# Credentials
- credentials were obtained through [![https://developer.spotify.com/dashboard]]
- - client id 
- - client secret
- A credentials.json files was created to store the credentials in a dictionary. 
- - This files was opened and keys: client_id and client_secret were found and passed through the spotify credentials manager. 

# Different Country Playlist
- Three different countries used: Mexico (`mexico_playlist`), United States (`us_playlist`), and United Kingdom (`playlist`) 
## Obtaining the data 
- Using a Virtual Protected Network (VPN) we were able to access spotifies API through different countries (i.e. Mexico, United States, and United Kingdom). Surfshark a subscription-based VPN was used to obtain the data.
- Featured Playlists were obtained in `NBO1-Data-Collection.ipynb`. We get featured playlists through the `playlist_info` function that returns the info of each playlist. We saved each of the playlist info into a list, and then dumped the dictionaries as json files in either (`mexico_playlist`), (`us_playlist`), and (`playlist`) depending on what country I set my VPN at. 

## Uploading to SQL
- Note the following was repeated three times (one for each country)
- Loading the files into `NB02-Data-Collection.ipynb`through the `load_files` function. Getting the artist info (genres), and creating a list with each of the playlists genres (according to the artist in the playlist). Dataframes were created to store data that would eventaully be uploaded to sql through the `to_sql` command. 
- - Three dataframes were created. playlist_category, playlist_name, and country. The country dataframe contains the name of the country and their id, which corresponds to c*. Where * = 1,2, or 3. 
- - Note each of the dataframes in playlist_category, and playlist_name contain a column named country_id. Whatever country is loaded through the VPN, the whole column would be filled with that specific country. Thus, we need to specify what country code is being added. 
- Note that when the dataframes are uploaded to sql, they are appending to each itself. i.e. the entire database is made up of three different dataframes which are different by their country id and category. 
- I did it in the order of United Kingdom, United States, then Mexico. 



