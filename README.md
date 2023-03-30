# FIFA_21_Data_Cleaning_Challenge

![image](https://user-images.githubusercontent.com/127632796/228795998-338f1229-2205-46a3-8b02-cc9e5db55961.png)

# INTRODUCTION

I was privileged to join a #datacleaningchallenge that was organized by @PromiseNonso on Twitter. This was my first cleaning project and I can say it was one of the dirtiest datasets I have seen so far.The dataset used is the FIFA-21 dataset that was gotten from [kaggle.com](https://www.kaggle.com/datasets/yagunnersya/fifa-21-messy-raw-dataset-for-cleaning-exploring). The challenge was to help data enthusiasts test the ability of beginners, intermediates and experts in turning the messy dataset into a clean one.

# DATASET DESCRIPTION

![image](https://user-images.githubusercontent.com/127632796/228798316-6f48d90e-06d0-4604-9223-22402b97a516.png)

The dataset used for this challenge is the Fifa-21 dataset. The dataset was obtained in its raw state after webscrapping from sofifa.com. It contains the details of football players alongside their performances. The dataset contains 18979 rows and 77 columns. The datafile also includes a data dictionary to further give the data analyst more insight on the player's information.

# DATA_CLEANING PROCESS

![image](https://user-images.githubusercontent.com/127632796/228799912-414d86d7-4307-495b-b2a0-197217c50a87.png)

# ID,NAME & LONG NAME:

The file was imported using the “get data from text/csv” to remove all the special characters. Duplicates were checked. The column ID is a “unique identifier” and the data type was changed to text. White spaces were removed from the name and long name by using the TRIM function and I also made use of the PROPER function to ensure the columns were in the right cases. The data types of the Name and Full name were converted to text and the Long name was renamed as Full name.

![picture 1](https://user-images.githubusercontent.com/127632796/228802585-66a3a96e-60ba-4aec-8c12-8c8ca4e53075.png)

# PLAYERURL, PHOTOURL AND NATIONALITY:

The playerurl and photourl contain the player's pictures and information. The data type was converted to text. The Column Nationality contains the country of origin for each player. This column was trimmed and the proper function was also used. The data type was changed to Text.

# AGE, OVA AND POT: 

The age column contains the age of the respective players and was originally in the text data type. The OVA and POT columns contain the overall player's performance. According to the data dictionary, these columns were supposed to be in percentage.

![picture 3](https://user-images.githubusercontent.com/127632796/228806011-7beffd40-7723-4bf3-810e-cd7eb8e95c63.png)

The Age column was converted to the number data type. The OVA and POT columns were converted to percentage by creating a new column and dividing the OVA and POT columns by 100 respectively. The data type was converted to percentage.

![picture 4](https://user-images.githubusercontent.com/127632796/228806514-c67a20e2-00f7-411d-8e48-ac3f4b8f4e94.png)

# CLUB AND CONTRACT:

Some of the cells in the Club column contain numerical prefix and also a wrong data type. The Contract column contains inconsistent data entries. It specifies players on lengthy contract, players that are free and players on loan.

![Screenshot (14)](https://user-images.githubusercontent.com/127632796/228808965-5e756f30-8b39-4115-84a7-54b08b03d80a.png)

The club column was Trimmed and the proper function was used. The inconsistent entries were corrected using the find and replace function. The Contract Year was separated using the Text to column to get the contractStartYear and ContractEndyear. The Contract Duration was gotten by subtracting the ContractEndYear from the ContractStartYear. The Contract Year of the footballers that were on loan was removed since this information was found in another column named "LoanEndDate".

![Screenshot (13)](https://user-images.githubusercontent.com/127632796/228811048-a219bce5-7da3-4ce9-b488-4b6444f0b960.png)


