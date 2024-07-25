LSE Data Science Institute | ME204 (2023/24) |

# **Final Assignment**

**DATE:** 25/07/2024

**AUTHOR:** Benjamin Pilnick

-----
_LSE ID: 202379847_

## About me!: 
- I am a Data Science and Economics Student from Northwestern University and I created this project as part of the LSE Summer School ME204 course (2024). I have always loved number and sports, and my eventaul career will be in sports data analysis where I can use my two passions. 

## Data 
- Source: Spotify API (Spotipy- python's package for Spotify API) 
    - [https://developer.spotify.com/documentation/web-api]

- I chose this datasource because I enjoy listening to music and always wondered what the categories of featured playlists were in the Spotify algorithm. This project attempts to investgate these categories along with the number of followers the playlsit has. 

- The most challenging part of collecting the data was the runtime. The Spotify API has a limit to how many requests a user can do, and I reached that limit multiple times. According to the documentation, the limit is described in 30 seconds intervals. Spotify does not list the actual number of requests allowed at a time. 

### Collecting the Data
- Data was collected by looking at the featured playlists, then obtaining the artists of all tracks in the playlist, and finding the categories of those artists. After obtaining all data, it was concatenated in a list. 
- Three different sets of data were used from United States, United Kingdom, and Mexico. A VPN was used to obtain data from these sources. 
- I collected the data through the Spotify API in predefined functions named `spotify.featured_playlist()`- which obtains the top 20 playlists in Spotify at the current time. This function was used in tandem with dumping the json files into the raw_data folder. Other functions include `spotify.artist()`- which obtains the info of the artist. Loading the data from json files located in raw_data/*_playlist we find the artist info such as their id, uri, and most importantly the genres. 
- See README.md for a more detailed analysis. 


## Key Findings: 
- Once data was cleaned using the Spotify API, and a database named playlist was created and loaded we graphed each country with their corresponding categories by count. 
- Main insights: 
    - According to Figure 1, 2, and 3 he most popular categories of artists in the featured playlists of different countries (United States, Mexico, and United Kingdom) is clearly Pop with Rap following. 
        - Pop consists of multiple subgenres, so it does not surprise me that it is the most popular category. Moreover, pop was popular across multiple different countries which gives evidence that pop is one of the most popular genres of music to listen to regardless of location. Music lovers around the globe can connect through their music. 
        - Like Pop, rap was also a popular genre. And rap conssits of mulitple subgenres like hip-hop rap, southern rap, and UK rap to name a few. 
    - United States and United Kingdom had almost identical data for their most popular categories(Figure 1 and 2)This gives light that the type of music listsened to in English countries are similar. This is a small sample size of only two countries. 

- Interesting findings: 
    - __United States__ 
        - In the United States it strikes me that one of the most popular genres of music that people listened was country. If we combine the country and southern country 16 tracks in the 20 playlists were from country artists as shown in Figure 3. 
    - __Mexico__ 
        - According to Figure 2 reggaeton a popular music category in music is a fusion of Jamaican dancehall and reggae. It has influences from both hip hop and classical rap. I did not know that this category existed until starting this data analysis. 
        - Sad sierrono is the only emotional genre listed in all the categories. It was the fourth most popular music genre with 15 different artists.
### Figure 1
<iframe src='about:blank' style='border:none !important;' width='600' height='400' srcdoc="&lt;html lang=&quot;en&quot;>
   &lt;head>
       &lt;meta charset=&quot;UTF-8&quot;>
       &lt;style> html, body { margin: 0; overflow: hidden; } &lt;/style>
       &lt;script type=&quot;text/javascript&quot; data-lets-plot-script=&quot;library&quot; src=&quot;https://cdn.jsdelivr.net/gh/JetBrains/lets-plot@v4.3.3/js-package/distr/lets-plot.min.js&quot;>&lt;/script>
   &lt;/head>
   &lt;body>
          &lt;div id=&quot;5D5jyv&quot;>&lt;/div>
   &lt;script type=&quot;text/javascript&quot; data-lets-plot-script=&quot;plot&quot;>
       var plotSpec={
&quot;data&quot;:{
&quot;category&quot;:[&quot;pop&quot;,&quot;rap&quot;,&quot;urbano latino&quot;,&quot;reggaeton&quot;,&quot;sad sierreno&quot;,&quot;corrido&quot;,&quot;sierreno&quot;,&quot;musica mexicana&quot;,&quot;corridos tumbados&quot;,&quot;norteno&quot;,&quot;reggaeton colombiano&quot;,&quot;argentine hip hop&quot;,&quot;reggaeton flow&quot;,&quot;banda&quot;,&quot;musica chihuahuense&quot;,&quot;urbano mexicano&quot;],
&quot;count&quot;:[96.0,50.0,17.0,15.0,14.0,13.0,13.0,12.0,12.0,11.0,10.0,10.0,9.0,9.0,8.0,7.0]
},
&quot;mapping&quot;:{
},
&quot;data_meta&quot;:{
},
&quot;guides&quot;:{
&quot;fill&quot;:&quot;none&quot;
},
&quot;ggtitle&quot;:{
&quot;text&quot;:&quot;Featured Playlist of Mexico by Genre&quot;
},
&quot;theme&quot;:{
&quot;axis_title_x&quot;:{
&quot;size&quot;:20.0,
&quot;blank&quot;:false
},
&quot;axis_title_y&quot;:{
&quot;size&quot;:20.0,
&quot;blank&quot;:false
},
&quot;plot_title&quot;:{
&quot;face&quot;:&quot;bold&quot;,
&quot;size&quot;:18.0,
&quot;hjust&quot;:0.1,
&quot;blank&quot;:false
}
},
&quot;kind&quot;:&quot;plot&quot;,
&quot;scales&quot;:[{
&quot;name&quot;:&quot;Count&quot;,
&quot;aesthetic&quot;:&quot;y&quot;
},{
&quot;name&quot;:&quot;Category&quot;,
&quot;aesthetic&quot;:&quot;x&quot;
}],
&quot;layers&quot;:[{
&quot;geom&quot;:&quot;bar&quot;,
&quot;stat&quot;:&quot;identity&quot;,
&quot;mapping&quot;:{
&quot;x&quot;:&quot;category&quot;,
&quot;y&quot;:&quot;count&quot;,
&quot;fill&quot;:&quot;category&quot;
},
&quot;data_meta&quot;:{
},
&quot;data&quot;:{
}
}],
&quot;metainfo_list&quot;:[]
};
       var plotContainer = document.getElementById(&quot;5D5jyv&quot;);
       LetsPlot.buildPlotFromProcessedSpecs(plotSpec, -1, -1, plotContainer);
   &lt;/script>
   &lt;/body>
&lt;/html>"></iframe>

### Figure 2 
<iframe src='about:blank' style='border:none !important;' width='600' height='400' srcdoc="&lt;html lang=&quot;en&quot;>
   &lt;head>
       &lt;meta charset=&quot;UTF-8&quot;>
       &lt;style> html, body { margin: 0; overflow: hidden; } &lt;/style>
       &lt;script type=&quot;text/javascript&quot; data-lets-plot-script=&quot;library&quot; src=&quot;https://cdn.jsdelivr.net/gh/JetBrains/lets-plot@v4.3.3/js-package/distr/lets-plot.min.js&quot;>&lt;/script>
   &lt;/head>
   &lt;body>
          &lt;div id=&quot;U664l3&quot;>&lt;/div>
   &lt;script type=&quot;text/javascript&quot; data-lets-plot-script=&quot;plot&quot;>
       var plotSpec={
&quot;data&quot;:{
&quot;category&quot;:[&quot;pop&quot;,&quot;rap&quot;,&quot;r&amp;b&quot;,&quot;hip hop&quot;,&quot;big room&quot;,&quot;edm&quot;,&quot;house&quot;,&quot;uk dance&quot;],
&quot;count&quot;:[151.0,57.0,9.0,8.0,7.0,7.0,6.0,6.0]
},
&quot;mapping&quot;:{
},
&quot;data_meta&quot;:{
},
&quot;guides&quot;:{
&quot;fill&quot;:&quot;none&quot;
},
&quot;ggtitle&quot;:{
&quot;text&quot;:&quot;Featured Playlist of United Kingdom by Genre&quot;
},
&quot;theme&quot;:{
&quot;axis_title_x&quot;:{
&quot;size&quot;:20.0,
&quot;blank&quot;:false
},
&quot;axis_title_y&quot;:{
&quot;size&quot;:20.0,
&quot;blank&quot;:false
},
&quot;plot_title&quot;:{
&quot;face&quot;:&quot;bold&quot;,
&quot;size&quot;:18.0,
&quot;hjust&quot;:0.1,
&quot;blank&quot;:false
}
},
&quot;kind&quot;:&quot;plot&quot;,
&quot;scales&quot;:[{
&quot;name&quot;:&quot;Count&quot;,
&quot;aesthetic&quot;:&quot;y&quot;
},{
&quot;name&quot;:&quot;Category&quot;,
&quot;aesthetic&quot;:&quot;x&quot;
}],
&quot;layers&quot;:[{
&quot;geom&quot;:&quot;bar&quot;,
&quot;stat&quot;:&quot;identity&quot;,
&quot;mapping&quot;:{
&quot;x&quot;:&quot;category&quot;,
&quot;y&quot;:&quot;count&quot;,
&quot;fill&quot;:&quot;category&quot;
},
&quot;data_meta&quot;:{
},
&quot;data&quot;:{
}
}],
&quot;metainfo_list&quot;:[]
};
       var plotContainer = document.getElementById(&quot;U664l3&quot;);
       LetsPlot.buildPlotFromProcessedSpecs(plotSpec, -1, -1, plotContainer);
   &lt;/script>
   &lt;/body>
&lt;/html>"></iframe>

### Figure 3
<iframe src='about:blank' style='border:none !important;' width='600' height='400' srcdoc="&lt;html lang=&quot;en&quot;>
   &lt;head>
       &lt;meta charset=&quot;UTF-8&quot;>
       &lt;style> html, body { margin: 0; overflow: hidden; } &lt;/style>
       &lt;script type=&quot;text/javascript&quot; data-lets-plot-script=&quot;library&quot; src=&quot;https://cdn.jsdelivr.net/gh/JetBrains/lets-plot@v4.3.3/js-package/distr/lets-plot.min.js&quot;>&lt;/script>
   &lt;/head>
   &lt;body>
          &lt;div id=&quot;IuPodu&quot;>&lt;/div>
   &lt;script type=&quot;text/javascript&quot; data-lets-plot-script=&quot;plot&quot;>
       var plotSpec={
&quot;data&quot;:{
&quot;category&quot;:[&quot;pop&quot;,&quot;rap&quot;,&quot;r&amp;b&quot;,&quot;contemporary country&quot;,&quot;hip hop&quot;,&quot;alt z&quot;,&quot;country&quot;,&quot;bronx drill&quot;,&quot;alternative r&amp;b&quot;,&quot;atl hip hop&quot;,&quot;classic oklahoma country&quot;,&quot;modern rock&quot;,&quot;urban contemporary&quot;,&quot;detroit hip hop&quot;,&quot;modern country rock&quot;,&quot;country road&quot;,&quot;tennessee hip hop&quot;,&quot;southern hip hop&quot;,&quot;conscious hip hop&quot;],
&quot;count&quot;:[142.0,99.0,10.0,9.0,8.0,7.0,7.0,7.0,7.0,6.0,6.0,6.0,6.0,6.0,6.0,6.0,6.0,6.0,6.0]
},
&quot;mapping&quot;:{
},
&quot;data_meta&quot;:{
},
&quot;guides&quot;:{
&quot;fill&quot;:&quot;none&quot;
},
&quot;ggtitle&quot;:{
&quot;text&quot;:&quot;Featured Playlist of United States by Genre&quot;
},
&quot;theme&quot;:{
&quot;axis_title_x&quot;:{
&quot;size&quot;:20.0,
&quot;blank&quot;:false
},
&quot;axis_title_y&quot;:{
&quot;size&quot;:20.0,
&quot;blank&quot;:false
},
&quot;plot_title&quot;:{
&quot;face&quot;:&quot;bold&quot;,
&quot;size&quot;:18.0,
&quot;hjust&quot;:0.1,
&quot;blank&quot;:false
}
},
&quot;kind&quot;:&quot;plot&quot;,
&quot;scales&quot;:[{
&quot;name&quot;:&quot;Count&quot;,
&quot;aesthetic&quot;:&quot;y&quot;
},{
&quot;name&quot;:&quot;Category&quot;,
&quot;aesthetic&quot;:&quot;x&quot;
}],
&quot;layers&quot;:[{
&quot;geom&quot;:&quot;bar&quot;,
&quot;stat&quot;:&quot;identity&quot;,
&quot;mapping&quot;:{
&quot;x&quot;:&quot;category&quot;,
&quot;y&quot;:&quot;count&quot;,
&quot;fill&quot;:&quot;category&quot;
},
&quot;data_meta&quot;:{
},
&quot;data&quot;:{
}
}],
&quot;metainfo_list&quot;:[]
};
       var plotContainer = document.getElementById(&quot;IuPodu&quot;);
       LetsPlot.buildPlotFromProcessedSpecs(plotSpec, -1, -1, plotContainer);
   &lt;/script>
   &lt;/body>
&lt;/html>"></iframe>


## Future 
- English Countries 
    - I would like to expand on my analysis of different English countries. I could look at all English-speaking countries such as Canada, Australia, and South Africa. 
    - This could be done by chaning VPN locations to these countries and repeating the same analysis that I have done. 

- Followers
    - Within the database in the playlist_name table, there is a column named followers. I would have liked to compare the values of playlists across different countries. For example, how would genre of the most followed playlist in the a country compare across countries. We could do this by writing a sql subquery that joins the playlist_name, playlist_category, and country tables. Then we would group by country, and get the playlist, country, and categories of that country. Since the group by on categorical columns will only return the first one, we would need to first order the subquery with followers desc. 
        - We would then investigate whether the categories would be different or the same for the most followed featured playlis. 

- Analyze pop genres
    - In our analysis we simplified the pop genres category by changing every line that contains pop with simply pop using `df_copy.loc[df_copy['categories'].str.contains('pop', case=False, na=False), 'categories'] = 'pop'`. If we were just to plot the genres of pop, how would our analysis change by country. Which type of pop would be the most popular? 


