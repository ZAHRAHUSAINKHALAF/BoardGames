![Heaser](images/Header2.jpg)

# BoardGames
An overall analysis on how to get into the board games market through Kickstarter website successfully

## DATA HANDLING PROCESS BY STEPS
- We began by filtering the dataset to include only entries under the "Games" category and the "Board Games" subcategory.
- We identified a duplicate subcategory due to a typo and merged it into a single, consistent "Board Games" subcategory.
- To estimate the launched date, we subtracted the duration (converted to integers for smoother calculations) from the funded date.
  ```
- The only null values were in the Location column. Since there were just 11 missing entries, we manually filled them by referencing the creators' websites.
- We removed one duplicate entry based on its unique ID.
- To simplify comparison, we cleaned the "Reward Levels" column, extracted the numeric values, and created two new columns representing the maximum and minimum reward amounts.


## DATA DICTIONARY

| Field                 | Description |
|-----------------------|------------|
| project id           | The unique identifier for each project on the Kickstarter platform. |
| name                 | The name of the project. |
| url                  | The link to the project's page on Kickstarter. |
| category             | The main category the project belongs to (e.g., Film, Music, Technology). |
| subcategory          | The more specific subcategory that defines the project's type in more detail. |
| location             | The city and state where the project originates. |
| status               | The status of the project (Successful, Failed, or still Active—“live”). |
| goal                 | The target amount of money the creator aims to raise through crowdfunding. |
| pledged              | The actual amount of money pledged by backers. |
| funded percentage    | The percentage of the goal that was funded. |
| backers              | The number of backers who contributed to the project. |
| funded date          | The date the project successfully met its funding goal (if applicable). |
| levels               | The number of reward tiers offered. |
| reward levels        | The different monetary values of rewards offered to backers. |
| updates              | The number of updates the creator posted. |
| comments             | The number of comments received on the project. |
| duration             | The number of days the project was active for funding. |
| launched date        | The date obtained by subtracting the duration from the funded date. |
| reward levels cleaned | To simplify the identification of minimum and maximum values. |
| reward_min           | The minimum reward value. |
| reward_max           | The maximum reward value. |
