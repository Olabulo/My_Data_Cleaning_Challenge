# FIFA_21_Data_Cleaning_Challenge

![image](https://user-images.githubusercontent.com/127632796/228795998-338f1229-2205-46a3-8b02-cc9e5db55961.png)

# INTRODUCTION:

I was privileged to join a #datacleaningchallenge that was organized by @PromiseNonso on Twitter. This was my first cleaning project and I can say it was one of the dirtiest datasets I have seen so far.The dataset used is the FIFA-21 dataset that was gotten from [kaggle.com](https://www.kaggle.com/datasets/yagunnersya/fifa-21-messy-raw-dataset-for-cleaning-exploring). The challenge was to help data enthusiasts test the ability of beginners, intermediates and experts in turning the messy dataset into a clean one. Microsoft Excel was the tool used for this task.

# DATASET DESCRIPTION:

![image](https://user-images.githubusercontent.com/127632796/228798316-6f48d90e-06d0-4604-9223-22402b97a516.png)

The dataset used for this challenge is the Fifa-21 dataset. The dataset was obtained in its raw state after webscrapping from sofifa.com. It contains the details of football players alongside their performances. The dataset contains 18979 rows and 77 columns. The datafile also includes a data dictionary to further give the data analyst more insight on the player's information.

# DATA_CLEANING PROCESS:

![image](https://user-images.githubusercontent.com/127632796/228799912-414d86d7-4307-495b-b2a0-197217c50a87.png)

# ID,NAME & LONG NAME:

The file was imported using the “get data from text/csv” to remove all the special characters. Duplicates were checked. The column ID is a “unique identifier” and the data type was changed to text. White spaces were removed from the name and long name by using the TRIM function and I also made use of the PROPER function to ensure the columns were in the right cases. The data types of the Name and Full name were converted to text and the Long name was renamed as Full name.

![picture 1](https://user-images.githubusercontent.com/127632796/228834248-ca1fad9b-0b81-4870-a9cd-b9b2291fc3e6.png)

# PLAYERURL, PHOTOURL AND NATIONALITY:

The playerurl and photourl contain the player's pictures and information. The data type was converted to text. The Column Nationality contains the country of origin for each player. This column was trimmed and the proper function was also used. The data type was changed to Text.

![PICTURE 2](https://user-images.githubusercontent.com/127632796/228811997-6fa022c5-e455-402c-a0e3-3b801d96bc88.png)

# AGE, OVA AND POT: 

The age column contains the age of the respective players and was originally in the text data type. The OVA and POT columns contain the overall player's performance. According to the data dictionary, these columns were supposed to be in percentage.

![picture 3](https://user-images.githubusercontent.com/127632796/228834483-ddea30ae-2a92-4d22-8ee4-6b0148647ea3.png)

The Age column was converted to the number data type. The OVA and POT columns were converted to percentage by creating a new column and dividing the OVA and POT columns by 100 respectively. The data type was converted to percentage.

![picture 4](https://user-images.githubusercontent.com/127632796/228834902-20b57511-c062-4fb5-b0d0-8c7ae97a212f.png)

# CLUB AND CONTRACT:

Some of the cells in the Club column contain numerical prefix and also a wrong data type. The Contract column contains inconsistent data entries. It specifies players on lengthy contract, players that are free and players on loan.

![Screenshot (14)](https://user-images.githubusercontent.com/127632796/228835249-effa456f-3a73-43e8-b58b-9cd049a0f8ac.png)

The club column was Trimmed and the proper function was used. The inconsistent entries were corrected using the find and replace function. The Contract Year was separated using the Text to column to get the contractStartYear and ContractEndyear. The Contract Duration was gotten by subtracting the ContractEndYear from the ContractStartYear. The Contract Year of the footballers that were on loan was removed since this information was found in another column named "LoanDateEnd".

![Screenshot (13)](https://user-images.githubusercontent.com/127632796/228835644-91d8ef3c-aa40-4904-8439-fbdd4efa5dbd.png)

# POSITION, HEIGHT AND WEIGHT:

The Position column contains one or more positions the players had ever played in. The Height column contains the player's height number. These values were written in two different data formats; the value in “cm”and the value in “ft and inches”.  The Weight column contains the weight number of each player which were written in two different formats; the values in “kg” and the values in “lbs".

![Screenshot (16)](https://user-images.githubusercontent.com/127632796/228813642-005480ca-a332-42e1-ad75-aad0555f4b50.png)

The Position Column was deleted as another column named “Best Position” also exist in the dataset which includes the best position fit for each player. For the Height column, I started by filtering out the values that contained "cm" and using the find and replace function to remove the cm. A new column was created where the function (=TRUNC(N2/2.54/12)&"' "&ROUND(MOD(N2/2.54,12),0)&"""") to convert to ft and inches. After that, I copied the data already in ft and inches and added them to the new column. Similarly, the weight column was corrected using the  IF statement to convert "kg" to "lbs". The values in kg under the weight column were multiplied by 2.205 since that is the standard convertion rate from kg to lbs.

![Screenshot (15)](https://user-images.githubusercontent.com/127632796/228816951-f4e88043-7a32-4ced-95fe-a18c19ef5697.png)

# BOV, BEST POSITION, JOINED AND LOANDATE END:

BOV, Best Position looks perfect but the data type was change. The Joined data type was changed to short date. The LoanDateEnd contains empty cells for players that were not on loan.The empty cells were replaced with "null" while the free players were replaced with "free".

![Screenshot (17)](https://user-images.githubusercontent.com/127632796/228836443-2e4114a4-ae0f-42c2-85ba-f9edf17411ac.png)

# VALUE, WAGE AND RELEASE CLAUSE:

The value, wage and Release Clause columns contained inconsistent data entries such as “M, K” where M represents million and K represents thousands.

![Screenshot (20)](https://user-images.githubusercontent.com/127632796/228821029-7bb0ae2a-ecdd-422f-a6cb-2c58a44ded7a.png)

The find and replace function was used to remove these inconsistencies from the cells, the M was replaced with  “000000” for millions and K was replaced with “000” for thousands respectively. The data type for the three columns was changed to accounting.

![Screenshot (19)](https://user-images.githubusercontent.com/127632796/228821948-79db7638-d8e9-4ccd-b165-5b1ca4730912.png)

The following columns 'Preferred Foot',‘Attacking’, ‘Crossing’, ‘Finishing’, ‘Heading Accuracy’, ‘Short Passing’, ‘Volley’, ‘Skill’, ‘Dribbling’, ‘Curve’, ‘FK_Accuracy’, ‘Long_Passing’, ‘Ball_Control’, ‘Movement’, ‘Acceleration’, ‘Sprint_Speed’, ‘Agility’, ‘Reaction’, ‘Balance’, ‘Power’, ‘Short_Power’, ‘Jumping’, ‘Stamina’, ‘Strength’, ‘Long_Shot’, ‘Mentality’, ‘Aggression’, ‘Interceptions’, ‘Positioning’, ‘Vision’, ‘Penalties’, ‘Composure’, ‘Defending’, Marking’, ‘Standing_Tackle’, ‘Sliding_Tackle’, ‘GoalKeeping’, ‘GK_Diving’, ‘GK_Handling’, ‘GK_Kicking’, ‘Gk_Positioning’, ‘GK_Reflexex’, ‘Total_Stats’, ‘Base_Stats’, ‘Attacking_Workrate’, ‘Defending_Workrate’, ‘PAC’, ‘SHO’, ‘DRI’, ‘DEF’, ‘PHY’, were all cleaned and the data type was changed

![Screenshot (24)](https://user-images.githubusercontent.com/127632796/228822614-3e427bb2-d0a5-41a8-8a9f-b85915e7972d.png)

# W/F, SM & IR:

The W/F, SM and IR contains ratings with a special character '★' and incorrect data type.

![Screenshot (31)](https://user-images.githubusercontent.com/127632796/228824247-589153d6-65ef-4aaf-b52b-a6d025e0e3e1.png)

The special character was deleted and the data type was changed to number.

![Screenshot (34)](https://user-images.githubusercontent.com/127632796/228824678-98ff4d39-878f-446f-97af-4874d711abf4.png)

# HITS:

The Hits Column contains inconsistent data entries where some of the cells contain 'K', where the K represents 'thousand'.The column data type was incorrect.

![Screenshot (37)](https://user-images.githubusercontent.com/127632796/228826194-b5317c63-fe8f-4602-835e-add23f271a00.png)

The IF Statement was used to multiply the values with 'K' by 1000 and the data type was corrected.

![Screenshot (39)](https://user-images.githubusercontent.com/127632796/228826687-caeb4065-e8d4-4c83-bdfc-292e1ea87985.png)

# CONCLUSION:

Having cross-checked my dataset for spelling errors, irrelevant data, duplicate, incorrect data type, outliers and empty cells, I can conclude that the dataset is now clean and can be used for analysis and visualization.
I am glad I was able to participate and learn so many things during the data cleaning process. I am open to correction or any addition.

Thank you for reading. For further information, kindly follow me on linkedin @ [DamilolaOlabulo] (http://linkedin.com/in/damilola-olabulo) and twitter @[OlabuloD.] (https://twitter.com/olabulod?s=11&t=i2ctVX8FrTDDa0EJgk9Rqw)
