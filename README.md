# BoardGames
An overall analysis on how to get into the board games market through Kickstarter website successfully

## DATA HANDLING PROCESS BY STEPS
- We began by filtering the dataset to include only entries under the "Games" category and the "Board Games" subcategory.
- We identified a duplicate subcategory due to a typo and merged it into a single, consistent "Board Games" subcategory.
- To estimate the launched date, we subtracted the duration (converted to integers for smoother calculations) from the funded date.
- The only null values were in the Location column. Since there were just 11 missing entries, we manually filled them by referencing the creators' websites.
- We removed one duplicate entry based on its unique ID.
- To simplify comparison, we cleaned the "Reward Levels" column, extracted the numeric values, and created two new columns representing the maximum and minimum reward amounts.
