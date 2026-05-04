# Machine learning based instagram marketing strategy

Python | Reinforcement Learning | Random Forest | Clustering | Instagram Analytics

This project builds an end-to-end machine learning pipeline that analyzes real Instagram post data, clusters engagement patterns, trains a supervised engagement-prediction model, and uses a Q-Learning reinforcement learning agent to recommend the **optimal posting strategy** — answering both **what to post** (image, carousel, or reel) and **when to post** (morning, afternoon, evening, or night).

The system demonstrates how combining unsupervised clustering, supervised prediction, and reinforcement learning can support data-driven social media strategy for brands in the consumer electronics space.

---

## Project Overview

Brands on Instagram need to make two key decisions for every post:

- **What to post** — image, carousel, or reel?
- **When to post** — which time of day drives the most engagement?

Wrong decisions lead to low reach, low likes, and wasted content effort.

This project builds an automated recommendation system that:

- processes and cleans raw Instagram post data across 4 brand hashtags
- engineers time-based features (hour, time of day, day of week)
- clusters posts into Low / Mid / High engagement segments using KMeans
- trains a Random Forest model to predict engagement for any (hashtag, time, media type) combination
- trains a Q-Learning RL agent over a 48-action space to learn the optimal posting strategy through trial and error
- produces a clear final recommendation with supporting visualizations

---

## Analysis Pipeline

The project follows a structured 4-notebook data science pipeline:

```
Raw Instagram CSV Data (4 hashtags)
↓
01 — Data Processing
     (clean, engineer features, standardize media_type)
↓
02 — Engagement Clustering
     (KMeans k=3 → Low / Mid / High clusters)
↓
03 — Supervised Engagement Model
     (Random Forest → predict engagement for 48 combinations)
↓
04 — Reinforcement Learning Agent
     (Q-Learning → learn optimal strategy over 500 episodes)
↓
Recommendation: What + When to Post
```

---

## Notebooks

| Notebook | Purpose | Key Output |
|----------|---------|------------|
| `01_data_processing.ipynb` | Load raw CSVs, clean data, engineer time features, EDA | `processed_data.csv` |
| `02_clustering.ipynb` | KMeans clustering on engagement, influencer profiling, media type × cluster analysis | `clustered_data.csv` |
| `03_supervised_model.ipynb` | Train Random Forest on 4 features, predict engagement for all 48 combinations | `model.pkl`, `encoder_maps.pkl` |
| `04_rl_agent.ipynb` | Q-Learning agent, 48-action space, heatmaps, policy map, final recommendation | Q-table, strategy recommendation |

---

## Hashtags Analyzed

The dataset covers Instagram posts for 4 tech brand hashtags:

- `#AppleEvent2025`
- `#MadeByGoogle`
- `#GalaxyS25`
- `#GalaxyS25Edge`

---

## Action Space

The RL agent learns over a **48-action space** — every possible combination of:

| Dimension | Options | Count |
|-----------|---------|-------|
| Hashtag | #AppleEvent2025, #MadeByGoogle, #GalaxyS25, #GalaxyS25Edge | 4 |
| Time of Day | morning, afternoon, evening, night | 4 |
| Media Type | image, carousel, reel | 3 |
| **Total** | | **48** |

---

## Supervised Model

The Random Forest regressor is trained on 4 features:

- `hashtag_encoded`
- `time_encoded`
- `media_type_encoded`
- `cluster` (engagement segment from KMeans)

It predicts engagement for all 48 combinations and ranks them. This prediction is also used as the **reward signal** for the RL agent.

---

## Reinforcement Learning Agent

The Q-Learning agent is configured as follows:

| Parameter | Value |
|-----------|-------|
| Algorithm | Tabular Q-Learning |
| State space | 48 (hashtag × time × media type) |
| Action space | 48 |
| Q-table shape | 48 × 48 |
| Episodes | 500 |
| Steps per episode | 10 |
| Learning rate (α) | 0.1 |
| Discount factor (γ) | 0.9 |
| Epsilon (start → min) | 1.0 → 0.05 |
| Epsilon decay | 0.995 |

The agent uses **epsilon-greedy exploration** — starting with full random exploration and gradually shifting to exploitation of the best-learned strategy.

---

## Model Evaluation

The Random Forest model is evaluated using:

- **MAE** — Mean Absolute Error
- **RMSE** — Root Mean Squared Error
- **R² Score** — Coefficient of determination

Feature importance is plotted to confirm which features drive engagement predictions.

The RL agent is evaluated via:

- **Learning curve** — reward and epsilon decay over 500 episodes
- **Q-table heatmaps** — one per media type (image / carousel / reel), showing max Q-value per hashtag × time slot
- **Policy map** — greedy policy decoded for all 48 states

---

## Final Recommendation

Both the Random Forest model and the RL agent independently agree on the #1 strategy:

```
==============================================================
   INSTAGRAM POSTING STRATEGY – RL RECOMMENDATION
==============================================================
  Hashtag      : #MadeByGoogle
  Time of Day  : Morning
  Media Type   : Reel
  Est. Engage. : ~179 interactions
==============================================================
```

> The RF model predicted this combination as #1 with 178.6 predicted engagement.
> The RL agent independently learned the same answer through 5,000 trial-and-error steps.
> Agreement between both models provides strong confidence in the recommendation.

---

## Dataset

**Raw Instagram Post Data** collected for 4 consumer electronics hashtags:

| File | Hashtag |
|------|---------|
| `data/df_apple.csv` | #AppleEvent2025 |
| `data/df_google.csv` | #MadeByGoogle |
| `data/df_s25.csv` | #GalaxyS25 |
| `data/df_s25_edge.csv` | #GalaxyS25Edge |

Each file contains post-level records including `like_count`, `comments_count`, `timestamp`, and `media_type`.

Additional files:

- `data/influencer_profiles.csv` — influencer account data
- `data/influencer_clustered.csv` — influencer tier clusters

---

## Running the Notebooks

Install dependencies:

```bash
pip install -r requirements.txt
```

Run notebooks in order:

```bash
jupyter notebook 01_data_processing.ipynb
jupyter notebook 02_clustering.ipynb
jupyter notebook 03_supervised_model.ipynb
jupyter notebook 04_rl_agent.ipynb
```

Or execute via terminal (recommended if Jupyter kernel has path issues):

```bash
python -m nbconvert --to notebook --execute --inplace --ExecutePreprocessor.timeout=300 "01_data_processing.ipynb"
python -m nbconvert --to notebook --execute --inplace --ExecutePreprocessor.timeout=300 "02_clustering.ipynb"
python -m nbconvert --to notebook --execute --inplace --ExecutePreprocessor.timeout=300 "03_supervised_model.ipynb"
python -m nbconvert --to notebook --execute --inplace --ExecutePreprocessor.timeout=300 "04_rl_agent.ipynb"
```

---

## Key Technologies

- Python
- Pandas
- NumPy
- Scikit-learn (KMeans, RandomForestRegressor)
- Matplotlib
- Seaborn
- Pickle
- Jupyter Notebooks

---

## Project Outcome

This project demonstrates how reinforcement learning can be applied to social media strategy optimization. By combining clustering, supervised prediction, and Q-Learning, the system moves beyond simple analytics to provide an **adaptive, learning-based recommendation** for what and when to post on Instagram.

The pipeline answers the client's core question:

> *"Which hashtag should I use, what type of content should I post, and at what time of day — to maximize engagement?"*

**Answer: Post a Reel using #MadeByGoogle in the Morning.**

---

