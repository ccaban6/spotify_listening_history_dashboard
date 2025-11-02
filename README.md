# Exploring 10 Years of My Spotify Listening History

## Summary

This interactive Tableau dashboard visualizes over ten years of my Spotify listening history, enriched with metadata from the Spotify API. It highlights how my music tastes have evolved over time and explores patterns in track popularity, completion behavior, and listening habits.

[![Tableau Public](https://img.shields.io/badge/View_on-Tableau_Public-blue)](https://public.tableau.com/views/spotify_list_hist_v2/Dashboard4?:language=en-US&publish=yes)

Key Skills: Python · SQL · Tableau · API Integration · Data Cleaning · Data Visualization

## Background

This data visualization project serves as a celebration of my decade-long Spotify listening history. Music is a hobby I’m deeply passionate about and explore regularly in my day-to-day life.

I’m fascinated by music not just for the atmosphere and emotion it conveys, but for its transformative power in defining “eras” of my personal taste and life. My journey with Spotify began around age 15 when I got my first real smartphone (*that wasn’t a flip phone*). Back then, my music world was limited to whatever I heard on the radio, from my siblings, or from classmates hyping up their favorite songs.

From those humble beginnings, different events in my life exposed me to new genres and artists, which in turn defined unique chapters in my listening history. For example, 2022 was a landmark year—my first full year living alone in college (*uninterrupted by COVID*)—and it also marked the beginning of my deep dive into K-POP. Today, that genre still plays a major role in my listening habits. To me, this illustrates how musical taste evolves with life experience.

## Project Preview

<a href="https://public.tableau.com/views/spotify_list_hist_v2/Dashboard4?:language=en-US&publish=yes" target="_blank" rel="noopener noreferrer">
  <img src="https://github.com/user-attachments/assets/8bae7507-3240-4fa4-b5e3-b70052cfbd6f" alt="Click to open dashboard">
</a>

> *Note: For best results, open the dashboard in Tableau Public. Clicking the image above will redirect you.*

This is my first Tableau project, and I focused on creating an interactive experience using filters, parameters, and dashboard actions. There are currently four main pages:

- **Home** – Overview of key stats like top tracks, top artists, and total minutes listened (inspired by Spotify Wrapped)
- **Popularity** – Density plots exploring how track and artist popularity relate to minutes played
- **Time** – Temporal filters (year, season, weekday, hour of day) to identify listening patterns
- **Completion** – Track and artist completion rates with optional temporal filters

## Data Sources

### 1. Extended Spotify Streaming History

- **Original Format:** Separate yearly `.csv` files downloaded from the [Spotify Privacy Portal](https://www.spotify.com/us/account/privacy/), later merged
- **Key Fields:**
  - `Album Name`, `Artist Name`, `Track Name`
  - `Conn Country`: Country of listening session
  - `Incognito Mode`: Whether session was incognito
  - `Offline`: Whether session was offline
  - `Platform`: Listening device/platform
  - `Reason Start`, `Reason End`: Track session behavior (e.g., autoplay, user-initiated, skipped, finished)
    - *For example, `trackend` typically means a track played to completion*
  - `Shuffle`, `Skipped`: Boolean indicators
  - `Spotify Track Uri`: Useful for API calls
  - `Ts`: Time played in milliseconds

### 2. Additional Artist & Track Metadata (via Spotify API)

- **Enriched using track IDs from streaming history**
- **Key Fields:**
  - `Track Popularity`, `Artist Popularity`: Spotify-defined popularity scores
  - `Duration Ms`: Duration of track
  - `Genres`: List of genres for each artist (*note: not all artists have genre tags*)

> *The files were later converted into .xlsx files to support relationships in Tableau. I found out that JSON files that are unioned weren't able to have relationships with other tables as well*

## Features

- Multi-dimensional filters for granular exploration
- Intuitive visuals that evolve with user interaction
- Completion analysis to understand listening habits beyond play counts
- Temporal insights revealing daily and seasonal trends

## Tools Used

- **Tableau Desktop/Public:** Visualization and dashboard development
- **Spotify API:** Metadata enrichment
- **Python:** Making API calls, joining the yearly files, loading data into MySQL database
- **MySQL:** Verified metrics and values shown in visualizations by comparing to queries made

## How to Use

1. Download your own Spotify data from: [Spotify Privacy Portal](https://www.spotify.com/us/account/privacy/)
2. Replace the `.csv` files in Tableau or adjust connections if you want to reuse the dashboard
> *Need to utilize the Spotify API to gather Track/Artist metadata* 
3. Explore the dashboard online or locally via Tableau Desktop

## Lessons Learned

- First hands-on experience with Tableau - new error codes unlocked!
- Gained insight into structuring interactive dashboards and data storytelling
- Reinforced the importance of clean, well-structured data for visual analytics

## Future Improvements

- Integrating various metrics besides minutes played, total tracks, and completion rate
- Focusing on the data in eras and performing more comparative analyses
- Providing more commentary similar to a report or presentation (personally feel that I am just presenting the data rather than providing my insights)


## Author

Created by Colin Caban – feel free to connect on GitHub or [LinkedIn](https://www.linkedin.com/in/colin-caban/).

---

