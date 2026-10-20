# 🎬 Unified Movie Recommender System

A Jupyter notebook that builds four movie recommendation engines on the TMDB 5000 dataset and combines them in an interactive widget.

## Engines
| Engine | Technique | Input |
|---|---|---|
| Collaborative filtering | Pearson correlation on a user–movie matrix | A movie you liked |
| Content-based | TF-IDF (unigrams + bigrams) with cosine similarity | A movie you liked |
| Emotion-based | Mood keywords mapped to genres | Free-text mood |
| Hybrid | Weighted mix of content similarity, mood match and quality score | Movie + mood |

## What's inside
- Data merge of `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv`
- Feature "soup" from genres, keywords, cast, director and overview, with stop-word removal and stemming
- Exploratory analysis: genres, ratings, releases per year, most-voted films
- IMDb-style Bayesian weighted rating to avoid ranking films with few votes highly
- Interactive `ipywidgets` interface and similarity heatmaps

## Run it
```bash
pip install pandas numpy scikit-learn matplotlib seaborn nltk ipywidgets
jupyter notebook movie_recommender_unified.ipynb
```
Keep the two CSV files in the same folder as the notebook.

## Limitations
- The collaborative engine uses a **simulated** user–movie matrix generated from TMDB vote data, because TMDB 5000 has no per-user ratings. Swapping in real ratings (e.g. MovieLens) would make it genuine.
- The emotion engine is keyword-based and is weak on some moods (horror, romance) and can repeat suggestions.

## Credits
Dataset: TMDB 5000 Movie Dataset. Approach adapted from [add article link].
