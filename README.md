sql-syntax-challenge

In this challenge, we’re going to practice performing SQL queries. This should help better solidify some concepts that were covered during lecture.
Assumptions

    You are using Postico
    You installed Postgres with homebrew
    Postgres is currently running on your computer

Setup

Follow the instructions below before continuing with this challenge.
Create your database, table, and data

We are creating a bank database with a single table (accounts) and 8 records. Please follow the instructions below to create a new database with this table and data.

    Open Postico, if needed.
    Connect to localhost.
    Click on the localhost tab/bar in the upper-left corner.
    Create a bank database
    Double-click the bank database to use it.
    Double-click the 'SQL Query' icon to bring up the query window.
    Paste the following query into the query box to create the accounts table and populate it with data. Remember to click the Execute query button.

CREATE TABLE accounts (
    user_id serial PRIMARY KEY,
    username varchar(12) NOT NULL,
    city varchar(128),
    transactions_completed integer,
    transactions_attempted integer,
    account_balance numeric(12,2)
);

INSERT INTO accounts (username, city, transactions_completed, transactions_attempted, account_balance) VALUES ('shawn', 'chicago', 5, 10, 355.80),
('cherise', 'minneapolis', 9, 9, 4000.00),
('larry', 'minneapolis', 3, 4, 77.01),
('dallas', 'new york', 6, 12, 0.99),
('anthony', 'chicago', 0, 0, 0.00),
('travis', 'miami', 10, 100, 500000.34),
('davey', 'chicago', 9, 99, 98.04),
('ora', 'phoenix', 88, 90, 3.33),
('grace', 'miami', 7, 9100, 34.78),
('hope', 'phoenix', 4, 10, 50.17);

GitHub repo

    Create a GitHub repo named “prime-solo-sql”.
    Create a file called “database.sql”. You will store your responses to the exercise questions here. NOTE: This is merely a text file with a .sql extension.

Exercise

For each of the following questions

    Write a comment that specifies which question you are answering. (SQL comments are two dashes, followed by text.)
    Write the SQL query that answers the question, below that comment.

Example question and answer

-- 0. How do you get all users?
SELECT * FROM accounts;

Base Mode Questions

    How do you get all users from Chicago?
    How do you get all users with usernames that contain the letter a?
    The bank is giving a new customer bonus! How do you update all records with an account balance of 0.00 and a transactions_attempted of 0? Give them a new account balance of 10.00.
    How do you select all users that have attempted 9 or more transactions?
    How do you get the username and account balance of the 3 users with the highest balances, sorted highest to lowest balance? NOTE: Research LIMIT
    How do you get the username and account balance of the 3 users with the lowest balances, sorted lowest to highest balance?
    How do you get all users with account balances that are more than $100?
    How do you add a new account?
    The bank is losing money in Miami and Phoenix and needs to unload low transaction customers: How do you delete users that reside in miami OR phoenix and have completed fewer than 5 transactions.

Stretch Goal Questions (word problems)

    Anthony moved to Santa Fe.
    Grace closed her account.
    Travis made a withdrawl of $20,000. What's their new balance? NOTE: Research RETURNING
    The Bank needs to track last names. NOTE: Research ALTER TABLE https://www.postgresql.org/docs/10/static/sql-altertable.html
