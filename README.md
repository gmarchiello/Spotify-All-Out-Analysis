# Analyzing Music Trends Across Decades: Insights from Spotify's "All Out" Playlists

## Project Overview

The "All Out" series of playlists on Spotify—such as "All Out 80s," "All Out 90s," and others—are curated collections that highlight iconic tracks from specific decades. These playlists serve as a valuable dataset for analyzing music trends, featuring influential songs that defined their eras and providing a nostalgic look at the music landscape.

This analysis goes beyond traditional metrics like tempo, loudness, and keys. By leveraging Spotify's audio features and metadata, we aim to uncover deeper insights into how music trends have evolved over time, identifying patterns that may not be immediately apparent from basic audio features alone. For detailed information on the available audio features, refer to the [Spotify API documentation](https://developer.spotify.com/documentation/web-api/).

 ## References to "All Out" Playlists

The analysis utilizes the following Spotify "All Out" playlists, each representing a distinct decade. These playlists are a rich source of data for understanding music trends over time:

- **1950s**: [All Out 50s](spotify:playlist:37i9dQZF1DWSV3Tk4GO2fq)
- **1960s**: [All Out 60s](spotify:playlist:37i9dQZF1DXaKIA8E7WcJj)
- **1970s**: [All Out 70s](spotify:playlist:37i9dQZF1DWTJ7xPn4vNaz)
- **1980s**: [All Out 80s](spotify:playlist:37i9dQZF1DX4UtSsGT1Sbe)
- **1990s**: [All Out 90s](spotify:playlist:37i9dQZF1DXbTxeAdrVG2l)
- **2000s**: [All Out 2000s](spotify:playlist:37i9dQZF1DX4o1oenSJRJd)
- **2010s**: [All Out 2010s](spotify:playlist:37i9dQZF1DX5Ejj0EkURtP)
- **2020s**: [All Out 2020s](spotify:playlist:37i9dQZF1DX2M1RktxUUHG)

## Spotipy

To interact with the Spotify API and retrieve data from these playlists, this project employs the **Spotipy** library. Spotipy is a lightweight Python library that simplifies the process of accessing the Spotify Web API, allowing for easy data retrieval and manipulation.

For more information on Spotipy, refer to the [Spotipy documentation](https://spotipy.readthedocs.io/en/2.19.0/).

## Mapping Tracks to Macro-Genres

To simplify our analysis, we categorize each track into predefined macro-genres based on their specific genres. This process involves:

1. **Identifying Songs with Unknown Genre**: We check for tracks labeled as "Unknown" and log their track ID, artist name, and song name. This helps pinpoint tracks that require further review.
  
2. **Assigning Genres**: For songs previously categorized as "Unknown," we manually research their genres and update the dataset accordingly.

3. **Extracting and Analyzing Unique Genres**: We compile all genres present in the dataset, count their occurrences, and prepare a list of unique genres to streamline subsequent analyses.


## Data Cleaning and Preparation

The data preparation phase involved several key tasks:

1. **Data Loading and Inspection**:
   - Loaded the dataset from the Spotify API and downloaded it as JSON (available in the repository).
   - Inspected the data to understand its structure and contents, opening the JSON file in a new notebook.

2. **Handling Genres**:
   - Manually substituted unknown genres.
   - Categorized 393 genres into 10 macro genres for better analysis.

3. **Handling Missing Values**:
   - Identified missing values within the dataset and applied appropriate strategies for imputation or removal.

4. **Identifying Outliers**:
   - Detected outliers that could skew the analysis and determined how to address them.

5. **Data Cleaning and Formatting**:
   - Ensured data consistency and accuracy by cleaning the dataset.
   - Reformatted data types where necessary (e.g., converting strings to datetime objects).
   - Removed duplicate entries to maintain data integrity.

## Exploratory Data Analysis

The exploratory data analysis (EDA) phase involved visualizing and summarizing the data to uncover patterns and insights. Key steps included:

- **Visualizations**: Created various plots to illustrate trends in audio features across different decades.
- **Statistical Analysis**: Conducted statistical tests to assess significant differences in audio characteristics between decades.
- **Correlation Analysis**: Investigated correlations among audio features to identify meaningful relationships.


## Observations from Genre Analysis

### Genre Trends Over Decades
- **Blues**: Prominent in the 1950s but declined sharply in subsequent decades.
- **Country and Folk**: Peaked in the 1960s, maintaining some presence into the 2020s.
- **Jazz**: Dominant in the 1950s, nearly disappearing by the 1990s.
- **Pop**: Consistently rising in popularity, with a slight dip in the 2000s.
- **Hip Hop**: Gained traction in the 1980s, continuing as a major genre.
- **R&B**: Fluctuated but peaked in the 1960s.
- **Reggae**: Steady presence, though never dominant.
- **Rock**: Reached its height in the 1970s, followed by a decline.
- **World Music**: Maintained a niche presence.

## Loudness Analysis

### Observations
- **1950s-1960s**: Average loudness around -9.7 dB to -9.8 dB.
- **1970s-1990s**: Noticeable increase in loudness, peaking at -5.42 dB in the 2000s.
- **2010s-2020s**: Slight decrease but remains higher than earlier decades.

This trend aligns with the phenomenon known as the "loudness war," where music production increasingly prioritizes higher loudness levels.

### Genre-Specific Loudness
- **Jazz**: Lowest average loudness at -10.58 dB.
- **Hip Hop/Rap** and **Electronic/Dance**: Highest average loudness at -5.90 dB.

## Tempo Analysis

### Observations
- Significant expansion in the range of tempos since the 1990s, particularly in the **Hip Hop/Rap** genre, which features slower beats and may have contributed to an overall decline in average tempo observed across decades.

## Duration of Tracks

### Observations
- Rising trend in track duration from the 1950s to the 1990s, with a notable decline in the 2000s and 2010s.

### Genre-Specific Track Durations
- **Rock** features the longest average durations, while **Jazz** and **World** have the shortest.

## Key Modes and Valence

### Observations
- **Major modes** comprise approximately 63.2% of the dataset, while **minor modes** account for about 36.8%.
- **Valence** indicates the musical positivity of a track, with major keys generally perceived as brighter and happier than minor keys.

### Valence Trends Over Decades
- Higher average valence observed in the 1950s and 1960s, with a decline noted from the 1990s onwards.

## Correlation Insights

### Excluded Correlations
Certain correlations were excluded to focus on more meaningful relationships:
- **Key Mode** and **Key**: Redundant correlation.
- **Release Year** and **Decade**: Closely related, providing limited additional insights.

### Key Observations
- Strong positive correlation between **energy** and **loudness** (0.68).
- Moderate negative correlation between **energy** and **acousticness** (-0.61).
- Positive correlation between **valence** and **danceability** (0.39), indicating happier songs are more danceable.

## Conclusion

This analysis provides valuable insights into the evolution of music trends across decades, illustrating shifts in genres, loudness, tempo, and other audio features. By examining these patterns, we gain a deeper understanding of how the music landscape has transformed over time.
