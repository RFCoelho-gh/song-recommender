# Spotify Song Recommendation System

A Python-based tool that provides personalized song recommendations by leveraging the Spotify API and a machine learning clustering model. This system identifies whether a song is part of the **Hot 100** list or suggests a song with similar musical features based on the user's input.

## Features

- **Hot Song Check**: Determines if the user's input is one of the top **Hot 100** songs.
- **Personalized Recommendations**: Suggests songs similar to the user's input based on Spotify's audio features.
- **Interactive Experience**: Displays recommendations with Spotify's embedded audio player.

## Core Functionality

The `get_recommendation()` function performs the following steps:

1. **User Input**:
   - Prompts the user to input a song title.

2. **Hot Song Check**:
   - Compares the input song against a predefined **Hot 100 Songs** list.
   - If the song is in the list, suggests another hot song randomly and embeds its audio for playback.

3. **Feature-Based Recommendation**:
   - If the input song isn't in the Hot 100:
     - Fetches its **Spotify audio features** (e.g., danceability, energy, tempo).
     - Scales these features using a pre-trained `scaler.pkl`.
     - Uses a pre-trained KMeans clustering model (`kmeans_model.pkl`) to find songs from the same cluster.
     - Recommends a song from the identified cluster and embeds its audio for playback.
