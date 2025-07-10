# Football Data Visualization

## Overview
This project provides a set of visualizations for football player data, including player positions on a football field, passing networks, heatmaps, and interactive player cards. It uses Python libraries to generate static and interactive plots, showcasing player statistics such as dribbles, assists, and other metrics.

## Features
- **Field Visualization**: Displays players on a football field with their positions, colored by dribbles and sized by assists.
- **Passing Network**: Visualizes passing interactions between players with line thickness indicating pass frequency.
- **Heatmap**: Generates kernel density estimation (KDE) heatmaps to show player activity areas.
- **Player Cards**: Creates detailed player cards with stats like goals, assists, market value, and contract details.
- **Interactive Visualization**: Uses Plotly to create an interactive field plot with hover data for player details.
- **Widget-Based Player Card Generator**: Allows users to create custom player cards using interactive widgets.

## Requirements
- Python 3.x
- Libraries: pandas, numpy, matplotlib, seaborn, plotly, pillow, requests, ipywidgets, nltk, country_converter
- Input files: CSV datasets (`attacking.csv`, `attempts.csv`, `defending.csv`, `disciplinary.csv`, `distributon.csv`, `goalkeeping.csv`, `goals.csv`, `key_stats.csv`)
- Image files: `saha1.png` (football field image) and player photos (e.g., `neuer.png`, `djk.png`, etc.)

## Installation
1. Clone the repository:
   ```
   git clone <repository-url>
   ```
2. Install dependencies:
   ```
   pip install pandas numpy matplotlib seaborn plotly pillow requests ipywidgets nltk country_converter
   ```
3. Download NLTK stopwords (if needed):
   ```python
   import nltk
   nltk.download('stopwords')
   ```
4. Ensure the required CSV files and image files are available in the project directory.

## Usage
1. Place the required CSV files and player images in the project directory.
2. Run the script:
   ```bash
   python football.py
   ```
3. The script generates:
   - Static plots saved as PNG files (`halisaha_oyuncu_dagilimi.png`, `halisaha_pas_isi_forma.png`, `halisaha_simulasyon.png`, `oyuncu_kartlari_yeni.png`)
   - An interactive HTML plot (`halisaha_interaktif_gelismis.html`)
   - An interactive widget interface for generating player cards

## Example
To visualize the player distribution and passing network:
```python
plt.figure(figsize=(15, 10))
ax = plt.gca()
add_field_background(ax)
for _, row in df.iterrows():
    x = np.random.normal(row["x"], 5, 100)
    y = np.random.normal(row["y"], 5, 100)
    sns.kdeplot(x=x, y=y, ax=ax, cmap="YlOrRd", alpha=0.3, levels=5, thresh=0.1)
plt.show()
```

To generate an interactive player card:
```python
display(name_dropdown, age_slider, value_dropdown, contract_dropdown, create_button)
```

## Output
- **Static Plots**: Visualizations of player positions, passing networks, and heatmaps saved as PNG files.
- **Interactive Plot**: An HTML file with an interactive football field showing player stats on hover.
- **Player Cards**: Static and interactive player cards displaying stats like goals, assists, market value, and contract end.

## Notes
- Ensure player images (`neuer.png`, `djk.png`, etc.) are available locally or provide valid URLs.
- The football field image (`saha1.png`) is required; a fallback URL is used if the local file is missing.
- The widget-based player card generator requires a Jupyter environment for interactivity.
- Adjust plot parameters (e.g., figure size, zoom) for better visualization on different displays.
