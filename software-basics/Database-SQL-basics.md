### What is a Database

Database is a place where a computer stores information in an organised way

Is like a digital notebook that never runs out of pages. Unlike a paper notebook, a database allows the computer to search, count, and sort information very quickly

#### example
* If a café has thousands of orders, a database can still answer question in seconds


#### commands used in VM (Café SQL)

* SELECT * ("*" symbol means all columns)
* FROM (word FROM tell the database which table to use)
* SELECT * FROM Orders; (shows every order stored)
* SELECT drink, price FROM Orders; (shows only the drink and price columns)
* WHERE (word WHERE filters rows)
* SELECT * FROM Orders WHERE drink = 'Coffee'; (if database has coffee orders it will show)
* SELECT * FROM Menu; (shows menu)
* ORDER BY (sorts results by column - lowest to highest by default)
* SELECT * FROM Orders ORDER BY price; (sorting order by price)
* SELECT * FROM Orders ORDER BY price DESC; (sort price by reverse order - highest to lowest)
* SELECT * FROM Orders WHERE drink = 'Coffee' ORDER BY price DESC; (combining filtering and sorting - filter one drink type and then sort by price)
* 
