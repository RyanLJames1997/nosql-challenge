# nosql-challenge

**Module 12 Challenge: UWA/edX Data Analytics Bootcamp**

Github repository at: [`nosql_challenge`](https://github.com/RyanLJames1997/nosql-challenge)

## Instructions

The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, `Eat Safe, Love`, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

## Contents

1. [`NoSQL_setup_starter.ipynb`](https://github.com/RyanLJames1997/nosql-challenge/blob/main/nosql_challenge/Starter_Code/NoSQL_setup_starter.ipynb) Jupyter Notebook database setup
2. [`NoSQL_analysis_starter.ipynb`](https://github.com/RyanLJames1997/nosql-challenge/blob/main/nosql_challenge/Starter_Code/NoSQL_analysis_starter.ipynb) Juypter Notebook for database analysis
3. Resources Folder with original [`establishments.json`](https://github.com/RyanLJames1997/nosql-challenge/blob/main/nosql_challenge/Starter_Code/Resources/establishments.json) file for import and analysis

## Repository Content

### Part 1: Database and Jupyter Notebook Set Up

- The test `"C:\Program Files\MongoDB\Server\7.0\bin\mongod.exe" --dbpath="c:\data\db"` was actioned in Terminal to ensure connection to MongoDB - thus, the importance of this step is to ensure the correct environment is established.
- [`NoSQL_setup_starter.ipynb`](https://github.com/RyanLJames1997/nosql-challenge/blob/main/nosql_challenge/Starter_Code/NoSQL_setup_starter.ipynb) provided the correct machine environment to import the provided [`establishments.json`](https://github.com/RyanLJames1997/nosql-challenge/blob/main/nosql_challenge/Starter_Code/Resources/establishments.json)
- Within the notebook, import `PyMongo` and `Pretty Print (pprint)`
- Confirm that the database created has the data loaded properly:
    - List the databases in `MongoDB`, therefore, `uk_food` must be listed.
    - List the collection(s) in the database to ensure `establishments` is there.
- Assign the  `estblishments` collection to a variable to prepare the collection for use.

### Part 2: Update and Database
- Use [`NoSQL_analysis_starter.ipynb`](https://github.com/RyanLJames1997/nosql-challenge/blob/main/nosql_challenge/Starter_Code/NoSQL_analysis_starter.ipynb) to conduct an indepth analysis.
- The magazine editors have some requested modifications for the database before you can perform any queries or analysis for them. Make the following changes to the `establishments` collection:
  - An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked you to include it in your analysis. Add the following information to the database:

```python
{"BusinessName":"Penang Flavours",
"BusinessType":"Restaurant/Cafe/Canteen",

    "BusinessTypeID":"",
    "AddressLine1":"Penang Flavours",
    "AddressLine2":"146A Plumstead Rd",
    "AddressLine3":"London",
    "AddressLine4":"",
    "PostCode":"SE18 7DY",
    "Phone":"",
    "LocalAuthorityCode":"511",
    "LocalAuthorityName":"Greenwich",
    "LocalAuthorityWebSite":"http://www.royalgreenwich.gov.uk",
    "LocalAuthorityEmailAddress":"health@royalgreenwich.gov.uk",
    "scores":{
        "Hygiene":"",
        "Structural":"",
        "ConfidenceInManagement":""
    },
    "SchemeType":"FHRS",
    "geocode":{
        "longitude":"0.08384000",
        "latitude":"51.49014200"
    },
    "RightToReply":"",
    "Distance":4623.9723280747176,
    "NewRatingPending":True
}
```

- Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the `BusinessTypeID` and `BusinessType` fields.
Update the new restaurant with the `BusinessTypeID` you found.

- The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.

- Some of the number values are stored as `strings`, when they should be stored as numbers, therefore:


    1. Use `update_many` to convert `latitude` and `longitude` to decimal numbers.
  
    2. Use `update_many` to convert `RatingValue` to integer numbers.

### Part 3: Exploratory Analysis



## References
