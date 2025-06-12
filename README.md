![Heaser](images/Header2.jpg)

# BoardGames
An overall analysis on how to get into the board games market through Kickstarter website successfully

## DATA HANDLING PROCESS BY STEPS
- We began by filtering the dataset to include only entries under the "Games" category and the "Board Games" subcategory.
- We identified a duplicate subcategory due to a typo and merged it into a single, consistent "Board Games" subcategory.
- To estimate the launched date, we subtracted the duration (converted to integers for smoother calculations) from the funded date.
''' import pandas as pd
import numpy as np
import re
# قراءة الملف
df = pd.read_excel('اسم_ملفك.xlsx')
# تحويل funded date لتاريخ
df['funded date'] = pd.to_datetime(df['funded date'])
# تحويل duration إلى int
df['duration'] = df['duration'].astype(int)
# حساب launched date
df['launched date'] = df['funded date'] - pd.to_timedelta(df['duration'], unit='D')
# استخراج reward levels
def extract_rewards(text):
    if pd.isna(text):
        return []
    text = str(text)
    matches = re.findall(r'\$?([\d,]+(?:\.\d+)?)', text)
    cleaned = []
    for match in matches:
        num = float(match.replace(',', ''))
        cleaned.append(num)
    return cleaned
df['reward list'] = df['reward levels'].apply(extract_rewards)
# حساب المين والمكس
df['reward_min'] = df['reward list'].apply(lambda x: min(x) if x else None)
df['reward_max'] = df['reward list'].apply(lambda x: max(x) if x else None)
# نحذف العمود المؤقت اللي يسبب لنا مشاكل بالحفظ
df.drop(['reward list'], axis=1, inplace=True)
# الحفظ النهائي
df.to_excel('kickstarter_cleaned_final.xlsx', index=False)
print(":rocket: الملف الجديد تم حفظه بشكل كامل وسليم!") '''
- The only null values were in the Location column. Since there were just 11 missing entries, we manually filled them by referencing the creators' websites.
- We removed one duplicate entry based on its unique ID.
- To simplify comparison, we cleaned the "Reward Levels" column, extracted the numeric values, and created two new columns representing the maximum and minimum reward amounts.
