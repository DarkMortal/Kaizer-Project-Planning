# Kaizer DB
## A lightweight and minimal csv database package
![logo](https://github.com/DarkMortal/Kaizer-DB/assets/67017303/cc9882fe-6980-4fcd-b211-bcdb5ea8d034)<br/>
<a href="https://www.buymeacoffee.com/darkmortal" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;"></a>
# Features
- SQL like syntax
- Works directly with CSV
- Supports all CRUD functionalities like INSERT, DELETE etc
# Drawbacks
- No type checking
- Only one query at a time
- Doesn't support data with spaces
# Getting started
  If you are using this package from the GitHub repository
  ```
    yarn start
  ```
  ```
    npm start
  ```
  If you are using this package from the npm repository
  ```
    require('kaizer-db')
  ```
  That's it! No fancy configuration or boiler code. It's as easy as that!!!
# Usage  
- Creating or using a database
  ```
    Use Database dbname;
  ```
  ```
    Create Database dbname;
  ```
  Both these commands create a new folder named ```dbname``` where the tables are stored as ```csv``` files.
- Show list of tables
  ```
    Show Tables;
  ```
  Shows list of available csv files in the current directory which is used as the database.
  
  ![first](https://github.com/DarkMortal/Kaizer-DB/assets/67017303/2006a7e7-0520-462c-8eac-67426b74605d)
- Creating a table
  ```
   Create Table Warriors (Name,Attack,Defense,PowerLevel);
  ```
  Creates a file named ```Warriors.csv``` in the current folder ```dbname``` with the given headers.
- Inserting data in a table
  ```
    Insert into Warriors (Name,Attack,Defense,PowerLevel) values (Goku,5000,7000,9001), (Vegeta,5000,7000,9000);
  ```
  Appends 2 records to the file named ```Warriors.csv```
- Getting records from a table
  ```
    Select * from Warriors;
  ```
  ![select1](https://github.com/DarkMortal/Kaizer-DB/assets/67017303/b3d27689-1abb-48b9-8f0a-ccd0cf3bb07c)
  ```
    Select Name, PowerLevel from Warriors;
  ```
  ![select2](https://github.com/DarkMortal/Kaizer-DB/assets/67017303/6b1c4dc2-2fb0-4255-86ae-333c859ab894)
- Getting records from a table using ```WHERE``` clause
  ```
    Select Name from Warriors Where PowerLevel > 9000;
  ```
  ![select3](https://github.com/DarkMortal/Kaizer-DB/assets/67017303/5c2061c0-22c5-4a62-945f-cd8005db062d)
- Getting records from a table using multiple ```WHERE``` clauses
  ```
    Select * from Warriors Where PowerLevel > 9000 and Name = Goku;
  ```
  ![where1](https://github.com/DarkMortal/Kaizer-DB/assets/67017303/c1f4c9cb-c021-444a-b442-e26bc4cc4f80)
  ```
    Select * from Warriors Where PowerLevel > 9000 or Name = Vegeta;
  ```
  ![where2](https://github.com/DarkMortal/Kaizer-DB/assets/67017303/ab74704e-74da-4f98-a556-20ad0eed7599)
- Updating a record using ```WHERE``` clause
  ```
    Update Table Warriors set PowerLevel = 10000, Defense = 8000 Where Name = Goku;
  ```
  ![updateQuery](https://github.com/DarkMortal/Kaizer-DB/assets/67017303/8d162f1d-4e86-47ad-82ea-a688d4fa5bd5)
- Deleting a record using ```WHERE``` clause

  ```
    Delete From Warriors Where PowerLevel < 10000;
  ```
  ![select5](https://github.com/DarkMortal/Kaizer-DB/assets/67017303/8929402f-e40d-4658-b849-ec95afffd4f0)
  ## Order by clause
  The default ordering is ascending order (`asc`,`Asc`,`ASC`)<br/>The descending order can be used as (`desc`,`Desc`,`DESC`)
  ### Examples
  ```
  Select * from test_data order by Defense;
  ```
  ![ser1](https://github.com/DarkMortal/Kaizer-DB/assets/67017303/d05a923f-52ba-4334-a5fb-04330fe89d4a)
  ```
  Select * from test_data where Attack > 200 order by Defense desc;
  ```
  ![ser2](https://github.com/DarkMortal/Kaizer-DB/assets/67017303/f356ba4b-4e94-4c93-a071-0cf6c446875a)
  ```
  Select Name, PowerLevel, Defense from test_data where Attack > 200 Order by Defense;
  ```
  ![ser3](https://github.com/DarkMortal/Kaizer-DB/assets/67017303/ebdf3c20-0e46-49b4-928a-83144f6f7f3f)
  ### Error handling
  ```
  > Select Name, PowerLevel from test_data where Attack > 200 Order by Defense;
  Error: Order by field needs to be included in fetch list
  ```
  The sorting column must be present in the list of columns that needs to be fetched.
## How to contribute
- Fork the [repository](https://github.com/DarkMortal/Kaizer-DB/) in your GitHub account.
- Make your changes.
- Submit a pull request.
- Code should well documented.
***
