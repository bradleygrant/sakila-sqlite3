# sakila-sqlite3

Sakila Sample Database - SQLite3 Port

Practice your SQL and Data Science Skills on this handy-to-use sample SQL dataset! Runs in SQLite3 on your local machine. No SQL server setup required.

Includes [Source Files](/source/) and a [Ready-To-Use SQLite3 Database File](sakila_master.db?raw=true)

## About Sakila

Sakila is a sample database originally developed by the MySQL development team. It provides data in a standard, well-normalized schema that can be used for examples in books, tutorials, articles, samples, and so forth.

Sakila models a database for a chain of video rental stores. It contains a vast amount of information about:

- movie titles
- actors, genres, etc.
- what stores have what films in inventory
- transactions and payments
- customers
- staff

What sets Sakila apart from other "toy" databases is the richness of its table schema, allowing SQL learners to practice fairly complex joins and queries on a compact dataset:

![Table schema UML diagram for the Sakila database](sakila.png)

The database definition files are open source via the New BSD license. Documentation and table descriptions are available [directly from the MySQL website.](https://dev.mysql.com/doc/sakila/en/sakila-introduction.html)


## About This SQLite3 Port

You're here because **you want to learn how to write SQL, not how to be a database administrator.**

I'm here to help you **get this sample dataset up and running on your machine in the next 5 minutes -- *without* installing a SQL server.**

The Sakila database source files were originally written in MySQL. SQLite is a more "generic" flavor than MySQL, so some source manipulation was required (thanks to the team at @jOOQ for that!)

For convenience, I am providing a master .db file that can be loaded directly into SQLite3 so you can take it and start running queries right away. 

## Usage

Before these steps, make sure you have SQLite3 on your computer. You can check by typing `sqlite3` at your terminal command prompt. (Then type `.quit` to exit.)

If necessary, install it from your apt/yum/homebrew package manager, or downloading it from the [SQLite website](https://www.sqlite.org/index.html). 

### Option 1: Download The Database File and Go!

If all you want to do is start practicing SQL queries, it's really easy:

1. Clone this repository to download the files. (Alternatively, just right-click and download [sakila_master.db](sakila_master.db?raw=true))

2. Open Sqlite3: `sqlite3 sakila_master.db`

3. **ANY CHANGES YOU MAKE WILL CHANGE THE MASTER.** To avoid this, clone the database file to create a working file:

```{sql}
sqlite> .clone sakila.db

sqlite> .open sakila.db
```
(or simply make a copy and rename it `sakila.db`)

4. Open this new file: `sqlite3 sakila.db`

Now you can run queries, insert, delete, drop and modify to your heart's content -- and you'll still have the `sakila_master.db` file as a backup so you don't have to worry about breaking anything!


### Option 2: Build The Database File From Source

If you want to try your hand at database management, try building the database from scratch with the included source files. Here's how to do that:

1. Clone this repository to download the files.

2. Open Sqlite3 in your terminal or command prompt.

3. Run the following commands to start a new database file, build the table schema, and insert all the data:

```{sql}
sqlite> .open sakila_master.db

sqlite> .read sqlite-sakila-schema.sql 

sqlite> .read sqlite-sakila-insert-data.sql 
```

4. Wait about 10 minutes.

5. Once the prompt returns, you're ready to write SQL!
