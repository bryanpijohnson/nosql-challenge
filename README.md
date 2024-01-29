# Bryan Johnson's GWU Module 12 NoSQL Assignent READ ME File

## The files for this assignment can be found at the following repo:
https://github.com/bryanpijohnson/nosql-challenge

## Within the repo link, you will find the following folders and files to be reviewed and graded:

- **README.md** - that is this file. :)
- **NOSQL Files** - this is the folder where the following files live:
    - **NoSQL_setup_starter.ipynb** - this file sets up the database into MongoDB, inserts the new document into the collection, removes a specific subsection of data, and updates some fields to the appropriate data types.
    - **NoSQL_analysis_starter.ipynb** - this file reestablishes a connection to the database, and then answers a number of questions, which have been answered below.
    - **Resources** - this folder holds the *establishments.json* file that creates the NoSQL database.
    - **.gitignore** - file that tells GitHub to ignore the original files, copies that I could go back to if I made any mistakes in the submitted files

---
### Database Set Up

I used the following command (within Python) to import the json file into the uk_food database:

`!mongoimport --type json -d uk_food --drop -c establishments --drop --jsonArray Resources/establishments.json`

I then set up a connection to the database to be used via Python.

I inserted the one document for "Penang Flavours" into the database then updated its "BusinessTypeID" to 1 after determining that other businesses of the same "BusinessType" had a value of 1.

Since the magazine isn't interested in establishments in Dover, I removed all documents with the LocalAuthorityName field equal to "Dover".

Lastly, I updated the datatype for the fields "Latitude", "Longitude", and "RatingValue" to "float", "float", and "int", respectively.

---
### Database Analysis

After setting up the connection to the database, I went and answered the following questions:

1. Which establishments have a hygiene score equal to 20?
    - The first 10 businesses with hygiene score of 20 are:
        1. The Chase Rest Home
        2. Brenalwood
        3. Melrose Hotel
        4. Seaford Pizza
        5. Golden Palace
        6. Ashby's Butchers
        7. South Sea Express Cuisine
        8. Golden Palace (another instance)
        9. The Tulip Tree
        10. F & S
2. Which establishments in London have a `RatingValue` greater than or equal to 4?
    - The first 10 businesses with `RatingValue` greater than or equal to 4 are:
        1. Charlie's
        2. Mv City Cruises Erasmus
        3. Benfleet Motor Yacht Club
        4. Coombs Catering t/a The Lock and Key
        5. Tilbury Seafarers Centre
        6. Mv Valulla
        7. Tereza Joanne
        8. Brick Lane Brews
        9. WH Smith
        10. The Nuance Group (UK) Limited
3. What are the top 5 establishments with a `RatingValue` of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flowers"?
    - The top 5 establishments with a `RatingValue` of 5, within 0.01 degrees of latitude and longitude from "Penang Flowers" are:
        1. Volunteer
        2. Plumstead Manor Nursery
        3. Atlantic Fish Bar
        4. Iceland
        5. Howe and Co Fish and Chips - Van 17
    - To solve this, I first looked up the latitude and longitude of "Penang Flowers" and saved those numbers as the latitude and longitude, respectively. I then used complex query to find the results, then sort and limit them.
4. How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.
    - There are 55 Local Authorities to have some establishments that have a hygiene score of 0. Overall, there 16827 establishments that have a hygiene score of 0.
    - The top ten Local Authorities that have establishments with a hygiene score of 0 (and their counts) are:
        1. Thanet (1130)
        2. Greenwich (882)
        3. Maidstone (713)
        4. Newham (711)
        5. Swale (686)
        6. Chelmsford (680)
        7. Medway (672)
        8. Bexley (607)
        9. Southend-On-Sea (586)
        10. Tendring (542)

This ends the analysis.

---
If you have any questions, please feel free to contact me.