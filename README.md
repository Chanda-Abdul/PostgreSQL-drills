# PostgreSQL-drills
PostgreSQL practice drills for Thinkful Mock Interview


In these drills, you'll practice executing basic CRUD (create, read, update, delete) operations in the psql shell. 

Before you get started, download this [SQL data dump](https://tf-assets-prod.s3.amazonaws.com/courses/node/assets/nyc-restaurants-data-backup.sql). Create and populate a new database using the data dump (make sure to update the path with the location where you saved the file):

```bash
psql -U dunder_mifflin_admin -d restaurants-app -f ~/Downloads/nyc-restaurants-data-backup.sql
```

Take a moment to get familiar with this new database. You can use `\dt+` to see a list of public tables and  `\d <TABLENAME>` to see a description of those tables.

Once you've successfully completed a drill, paste your query into a Gist to reference later on.

## 1. Get all restaurants

Write a query that returns all of the restaurants, with all of the fields.

````SELECT * from restaurants;````

## 2. Get Italian restaurants

Write a query that returns all of the Italian restaurants, with all of the fields

````
SELECT * FROM restaurants 
WHERE cuisine = 'Italian';
````

## 3. Get 10 Italian restaurants, subset of fields

Write a query that gets 10 Italian restaurants, returning only the id and name fields.

## 4. Count of Thai restaurants

Write a query that returns the number of Thai restaurants.

## 5. Count of restaurants

Write a query that returns the total number of restaurants.

## 6. Count of Thai restaurants in zip code

Write a query that returns the number of Thai restaurants in the 11372 zip code.

## 7. Italian restaurants in one of several zip codes

Write a query that returns the id and name of five Italian restaurants in the 10012, 10013, or 10014 zip codes. The initial results (before limiting to five) should be alphabetically sorted.

## 8. Create a restaurant

Create a restaurant with the following properties:

```
name: 'Byte Cafe',
borough: 'Brooklyn',
cuisine: 'coffee',
address_building_number: '123',
address_street: 'Atlantic Avenue',
address_zipcode: '11231'
```


## 9. Create a restaurant and return id and name

Create a restaurant with values of your choosing, and return the id and name.

## 10. Create three restaurants and return id and name

Create three restaurants using a single command, with values of your choosing, returning the id and name of each restaurant.

## 11. Update a record

Update the record whose value for `nyc_restaurant_id` is '30191841'. Change the `name` from 'Dj Reynolds Pub And Restaurant' to 'DJ Reynolds Pub and Restaurant'.

## 12. Delete by `id`

Delete the grade whose `id` is 10.

## 13. A blocked delete

Try deleting the restaurant with `id` of `22`. What error do you get?

Paste the error text for the answer. We'll learn about foreign key constraints in the next reading, but take two seconds and come up with your own theory about what this message means.


## 14. Create a table

Create a new table called `inspectors` with the following properties:

```
first_name: String of inspector's first name, required
last_name: String of inspector's last name, required
borough: The borough the inspector works in, not required, one of Bronx, Brooklyn, Manhattan, Queens, Staten Island.
```

`inspectors` should also have a system generated primary key property, `id`.

Note that the `borough` property requires you to use an [enumerated type](https://www.postgresql.org/docs/current/static/datatype-enum.html), which is a list of set values you can use for a property. You can use an existing enumerated type that will already be in the table: `borough_options`.

## 15. Update a table

Add a `notes` field to the `grades` table. `notes` are not required, and are text.

## 16. Drop a table

Drop the `inspectors` table from the database.

