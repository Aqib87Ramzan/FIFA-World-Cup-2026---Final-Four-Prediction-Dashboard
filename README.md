# 🏆 FIFA World Cup 2026 – Final Four Prediction

A data-driven prediction model for the 2026 FIFA World Cup semifinalists — **France, Argentina, Spain, and England** — using historical World Cup data and a Monte Carlo simulation.

## 📊 Project Overview

This project predicts the likely winner of the 2026 World Cup by:
1. Building team attack/defense strength ratings from historical goal-scoring data
2. Simulating the actual semifinal bracket thousands of times using a Poisson-based statistical model
3. Visualizing the results in an interactive Power BI dashboard

## 🧠 Methodology

- **Data source:** [A Comprehensive Database on the FIFA World Cup](https://www.kaggle.com/datasets/joshfjelstul/world-cup-database) (Fjelstul World Cup Database), covering all World Cups from 1930–2022.
- **Team strength ratings:** Each team's attack and defense rating is calculated from their historical goals scored/conceded per match, relative to the tournament-wide average. Recent tournaments are weighted more heavily than older ones (recency weighting) since squads and playing styles evolve over time.
- **Match simulation:** Goals in each simulated match are drawn from a Poisson distribution based on each team's expected goals — the standard statistical approach for modeling football scorelines. Knockout draws are resolved via a penalty-shootout coin flip weighted slightly by attack rating.
- **Monte Carlo simulation:** The semifinal bracket (France vs. Spain, England vs. Argentina → Final) is simulated 50,000 times. The percentage of simulations each team wins the tournament is used as their predicted win probability.

## 📈 Results

| Team | Reach Final % | Win World Cup % |
|------|---------------|------------------|
| France | 57.59% | **33.79%** |
| Argentina | 53.43% | 24.41% |
| Spain | 42.41% | 22.11% |
| England | 46.57% | 19.70% |

**Predicted Champion: France** 🏆

## 🛠️ Tools Used

- **Python** (Pandas, NumPy) — data processing, feature engineering, and Monte Carlo simulation
- **Power BI** — interactive dashboard and visualizations

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `world_cup_prediction.ipynb` | Full Python notebook — data loading, ratings, simulation, export |
| `team_strength_ratings.csv` | Historical attack/defense ratings for all World Cup teams |
| `team_appearances_with_weights.csv` | Match-level team data with recency weights applied |
| `world_cup_2026_prediction.csv` | Final predicted probabilities for the 4 semifinalists |
| `dashboard.pbix` | Power BI dashboard file |

## 📊 Dashboard Preview

The Power BI dashboard includes:
- Predicted champion and win probability cards
- World Cup winning probability bar chart
- Reach-final probability bar chart
- Attack vs. defense rating scatter plot
- Full team comparison table

## ⚠️ Limitations

- Predictions are based on historical goal-scoring data through 2018 and do not account for current squad form, injuries, or in-tournament momentum in 2026.
- Penalty shootouts are approximated as a weighted coin flip rather than modeled independently.
- Team strength is based purely on past World Cup performance, not domestic league form, FIFA rankings, or other external factors.

## 🙌 Acknowledgements

Special thanks to **Muhammad Bakht** for the guidance and support on this project.

## 📄 License

This project is for educational and portfolio purposes. Data sourced from the [Fjelstul World Cup Database](https://www.kaggle.com/datasets/joshfjelstul/world-cup-database) on Kaggle.
