
# StockXplorer

StockXplorer is a simple stock management and user authentication system built using SQLite databases. It allows users to perform CRUD operations on stock data and provides user authentication for both admins and regular users.

## Table of Contents

1. [Introduction](#introduction)
2. [Database Structure](#database-structure)
3. [Authentication](#authentication)
4. [CRUD Operations for Admin](#crud-operations-for-admin)
5. [Read access for user](#Read_access_for_user)
6. [Stock Operations](#stock-operations)
7. [User Registration](#user-registration)
8. [Main Menu](#main-menu)
9. [Closing Connections](#closing-connections)
10. [Installation](#installation)


## Introduction

StockXplorer is a lightweight application that facilitates stock data management and user authentication. It is designed with simplicity and ease of use in mind, providing a set of features for both administrators and regular users.

## Database Structure

StockXplorer uses three SQLite databases:

- `stocks.db` for stock-related data.
- `users.db` for user data.
- `admins.db` for admin data.

### Stock Data Table

The `Stock_Data` table in `stockxplorer.db` includes the following columns:

- Ticker (TEXT)
- Date (TEXT)
- Open (REAL)
- High (REAL)
- Low (REAL)
- Close (REAL)
- AdjClose (REAL)
- Volume (INTEGER)

The combination of Ticker and Date is enforced as unique.

### Users Table

The `Users` table in `users.db` includes the following columns:

- user_id (INTEGER, PRIMARY KEY)
- username (TEXT)
- password (TEXT)

### Admins Table

The `admins` table in `admins.db` includes the following columns:

- admin_id (INTEGER, PRIMARY KEY)
- username (TEXT)
- password (TEXT)

## Authentication

The `authenticate` function is responsible for checking user credentials against the appropriate database (either `users.db` or `admins.db`). It returns a boolean indicating success and the user/admin ID if authentication is successful.

## CRUD Operations for Admin

Admins have access to CRUD operations on stock data. The operations include:

1. **Create Stock Entry**: Adds a new stock entry to the `Stock_Data` table.
2. **Read Stock Data**: Retrieves historical stock data based on specified criteria.
3. **Update Stock Entry**: Modifies the details of an existing stock entry.
4. **Delete Stock Entry**: Removes a specific stock entry from the dataset.

## Stock Operations

Users can interact with the stock data by:

- Creating new stock entries.
- Reading historical stock data based on specific criteria.
- Updating existing stock entries.
- Deleting stock entries.
- 
## Read access for user

1. **Read Stock Data**: Retrieves historical stock data based on specified criteria.

## User Registration

The `user_registration` function allows users to register by providing a username and password. The system checks for duplicate usernames before creating a new user.

## Main Menu

The `main_menu` function presents a menu to users, allowing them to choose between admin login, user login, user registration, or exit.

## Closing Connections

The application ensures proper closure of database connections (`stock_conn`, `user_conn`) upon program exit.

## Installation

Ensure you have Python and SQLite installed. Clone the repository and run the application.

```bash
git clone https://github.com/yourusername/StockXplorer.git
cd StockXplorer

