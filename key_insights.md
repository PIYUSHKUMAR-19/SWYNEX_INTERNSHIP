# Key Insights — Chess Game Analysis

## 1. Distribution of Game Outcomes

The dataset contains 19,524 chess-game records. The recorded outcomes are distributed as follows:

| Outcome | Number of Games | Percentage of All Records |
|---|---:|---:|
| White Wins | 9,617 | 49.26% |
| Black Wins | 8,787 | 45.01% |
| Draws | 901 | 4.61% |
| Unknown/Other Outcomes | 219 | 1.12% |
| **Total** | **19,524** | **100.00%** |

### Key Observation

White won more games than Black in this dataset. Among the 18,404 decisive games (games won by either White or Black), White accounted for approximately 52.25% of wins, while Black accounted for 47.75%.

### Interpretation

The observed records show a higher number of White wins than Black wins. However, this descriptive analysis alone does not prove that playing White causes a higher probability of winning.

### Business/Analytical Relevance

This finding provides a starting point for further analysis of game outcomes by player rating, opening choice, and recorded game length.

### Data Note

Unknown or other outcomes account for 219 records. These are retained as a separate category rather than incorrectly assigning them to White wins, Black wins, or draws.








## 2. Relationship Between Rating Advantage and Winning

### Key Finding

Among decisive games where one player had a validated rating advantage of at least 200 points, the higher-rated side won 4,579 out of 5,768 games, approximately 79.39%.

| Metric | Result |
|---|---:|
| Decisive games analyzed | 5,768 |
| Wins by the higher-rated side | 4,579 |
| Win share in this group | 79.39% |

### Interpretation

In this subset of the dataset, the side with a rating advantage of at least 200 points won a large majority of decisive games. This suggests an association between a substantial rating advantage and winning.

### Analytical Relevance

This comparison helps investigate whether differences in player ratings are associated with game outcomes. It can guide further analysis by rating-advantage category and outcome type.

### Limitation

This is an observational finding, not proof of causation. It applies only to the qualifying decisive games with usable, validated ratings. Draws are excluded from the decisive-game denominator, and games without a valid rating-advantage classification are not included in this comparison.






## 3. Relationship Between Recorded Game Length and Draws

### Key Finding

The EDA reports the following approximate draw shares across two recorded-move groups:

| Recorded-Move Group | Approximate Draw Share |
|---|---:|
| 41–60 moves | 2% |
| 151–349 moves | 23% |

### Interpretation

The observed draw share is higher in the 151–349 recorded-move group than in the 41–60 group. This indicates that game outcomes vary across the recorded-move categories in this dataset.

### Analytical Relevance

Comparing game length with outcomes can help identify patterns in how games conclude and guide further investigation of draws, resignations, and checkmates across move-count groups.

### Limitation

These percentages describe an association and do not establish that longer games cause draws. The 151–349 group has a smaller sample, so its underlying game count should be reviewed before drawing strong conclusions. The move count is derived from recorded notation and may not be equivalent to full numbered turns.






## 4. Chess Opening Variety

### Key Finding

The ten most frequent opening labels account for approximately 2,535 games, representing 12.98% of the 19,524 records.

| Metric | Result |
|---|---:|
| Total game records | 19,524 |
| Games associated with the ten most frequent opening labels | Approximately 2,535 |
| Share of all game records | Approximately 12.98% |

### Interpretation

The ten most frequent opening labels account for a relatively small share of the dataset. This suggests that the recorded games are distributed across many opening categories rather than being concentrated exclusively in the top ten labels.

### Analytical Relevance

Opening-frequency analysis can help identify commonly recorded openings and support further comparisons between opening categories and game outcomes.

### Limitation

Opening labels may contain inconsistent capitalization or leading and trailing spaces. These inconsistencies can cause the same opening to appear under multiple labels and affect frequency rankings. Standardizing the labels is recommended before making definitive comparisons.







## 5. Monthly Game Record Volume

### Key Finding

August 2017 has a noticeably higher number of recorded games than the adjacent months in this dataset.

| Month | Number of Records |
|---|---:|
| July 2017 | 1,637 |
| August 2017 | 5,411 |
| September 2017 | 1,423 |

August accounts for approximately 27.85% of the 19,426 records with valid creation timestamps.

### Interpretation

The dataset shows a pronounced concentration of records in August 2017 compared with July and September. This is a pattern in the available data, but it does not necessarily mean that actual chess-playing activity increased during that month.

### Analytical Relevance

Monthly aggregation helps identify changes in recorded data volume and can guide checks for sampling patterns, collection periods, and gaps in date coverage.

### Limitation

The spike may reflect the way the dataset was collected, sampled, or assembled. The available records alone cannot establish the cause of this concentration or prove a real-world increase in chess activity. This comparison is based on records with valid creation timestamps.







## 6. Game Termination Reasons

### Key Finding

The termination-reason summary in the EDA identifies resignation as the most frequent recorded reason, followed by checkmate. Unknown termination reasons remain a separate category.

### Interpretation

The recorded data indicates that resignation and checkmate are important categories among the observed game-ending reasons. However, the exact number and percentage for each category should be taken from the final, refreshed EDA summary before reporting numerical comparisons.

### Analytical Relevance

Understanding how games end can help describe outcome patterns and support comparisons between termination reasons, recorded game length, and game outcomes.

### Data Quality Note

Some records have unknown or unavailable termination reasons. These should remain explicitly identified rather than being assigned to resignation, checkmate, or another category without evidence.

### Limitation

This is a descriptive finding about the available dataset. It does not establish why players chose a particular way to end a game. Confirm the final category counts and percentages against the workbook before publishing them.







## Overall Conclusion

This project demonstrates how data cleaning, exploratory data analysis, and visualization can turn chess-game records into meaningful observations. The analysis examined game outcomes, player-rating differences, recorded game length, opening frequency, monthly record volume, and termination reasons.

The dataset recorded more wins by White than Black, an association between substantial rating advantages and winning among qualifying decisive games, variation in draw shares across recorded-move groups, and a notable concentration of records in August 2017. These results describe patterns in the available dataset and provide opportunities for further investigation.

## Limitations of the Analysis

- **Missing information:** Some records have missing timestamps, unknown rated status, or unavailable termination information.
- **Rating validation:** Rating comparisons depend on the project’s screening rules and on having usable ratings for both players.
- **Recorded move counts:** Move counts derived from notation may not be equivalent to full numbered turns.
- **Dataset composition:** The concentration of records in August 2017 may reflect collection or sampling effects rather than a real-world increase in chess activity.
- **Descriptive analysis:** The results identify patterns and associations; they do not establish causation.
- **Validation before publication:** Refresh the relevant PivotTables and verify key counts, percentages, and chart totals against the final workbook before publishing the project.

## Final Note

All numerical findings should be interpreted in the context of the available data and its quality limitations. The project prioritizes transparent data handling, evidence-based conclusions, and clear communication of uncertainty.





