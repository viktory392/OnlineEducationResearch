# Statistical Evaluation of Students' Performance in Online Education

This research analyzes student performance and behavior on the Junyi Academy platform, using statistical testing and regression modeling to demonstrate that higher mastery—evidenced by leveling up—is strongly correlated with decreased time spent and reduced hint usage.

*This work was performed by [Vikraanth Sinha](https://www.vikraanth.com), under the guidance of Professor Joy Lu and PhD student Angela Xiao, at Carnegie Mellon University's Tepper School of Business.*

___

## 1. Student Performance and Grade Levels

The data reveals a consistent trend where performance metrics shift as students progress through grades.

* **Difficulty Scaling**: Students in higher grade levels generally take more time to answer questions and have lower accuracy rates (percent correct). This suggests that question difficulty increases more rapidly than student proficiency as grade levels rise.
* **Statistical Significance**: A one-way ANOVA and Dunnett's Test confirmed significant differences in performance across grade levels.
* **Interaction Effects**: Visualizations indicate interactions between gender and grade level regarding performance, though specific trends vary.

## 2. The "Leveling" Mechanism (Upgrades and Downgrades)

A significant portion of the analysis focused on what happens immediately before a student "levels up."

* **Predictors of Success**: T-tests comparing "before upgrade" sessions to "other" sessions show that students take significantly less time and use fewer hints immediately before they level up.
* **Behavioral Indicators**: As students progress through a specific problem set, their performance tends to improve. Their time spent, number of attempts, and number of hints decrease, indicating a growth in confidence and mastery.
* **Sparsity of Downgrades**: Data on "leveling down" was extremely sparse, making it difficult to draw statistically significant conclusions about student behavior prior to a downgrade.

## 3. Impact of Being "Self-Coached"

The analysis compared students who are self-taught (self-coaches) vs. those who are not.

* **Performance Gap**: Initial t-tests suggested that self-taught students perform better, take less time, and are more consistent than those taught by others.
* **Reliability Warning**: Only 7 out of 1000 students in the subset were identified as self-taught, so these results may not be representative of the broader population.

## 4. Key Correlations and Predictors

Regression and correlation analyses were used to identify what factors most influence student success:

* **Correctness and Time**: There is a strong inverse relationship between correctness and time; correctly answered problems consistently show much lower durations than incorrect ones.
* **Hint Usage**: Interestingly, the "correct" indicator in this dataset often requires the student to answer on the first attempt without using hints. Consequently, hint usage is higher in "incorrect" categories by definition.
* **Multicollinearity**: `avg_hint_cnt` and `percent_hint_used` are highly correlated, so they should not both be used in the same regression model to avoid statistical errors.

## 5. Summary of Statistical Models

| Model Target | Key Predictors | Finding |
| :--- | :--- | :--- |
| **Percent Correct** | `avg_attempt_cnt`, `avg_hint_cnt` | Higher attempts/hints strongly correlate with lower accuracy. |
| **Level Change** | `avg_duration`, `percent_hint_used` | Used to determine which behaviors lead to the most "leveling up" progress. |
| **Points** | `has_teacher_cnt` | Explored the impact of social support on total points earned. |
