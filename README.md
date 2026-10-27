# SideQuest

**SideQuest - Your Middleman.** A PHP/HTML/CSS group project that connects clients who post "quests" (paid tasks) with service providers who take them on.

## Tech stack

- PHP 8.2
- MariaDB / MySQL (through XAMPP)
- HTML and CSS

## Project files

| File | Purpose |
| --- | --- |
| `SideQuest.php` | Main page |
| `connectscript.php` | Database connection (included by the pages) |
| `style.css` | Stylesheet |
| `sidequestdb.sql` | Database export to import into XAMPP |

## Database

The `sidequestdb` database has four tables:

| Table | Description |
| --- | --- |
| `clientside` | Client accounts (`UserID`, `username`, `password`) |
| `serviceside` | Service provider accounts (`proID`, `pro_username`, `pro_pass`, `credential_file`) |
| `quest` | Quests posted by clients (`questID`, `UserID`, `amount`, `description`) |
| `transaction` | Links a client to a service provider (`transactionID`, `UserID`, `proID`) |

## Setup

1. Install [XAMPP](https://www.apachefriends.org/) and start **Apache** and **MySQL** from the XAMPP Control Panel.
2. Clone the repository into XAMPP's `htdocs` folder:
   ```
   cd C:\xampp\htdocs
   git clone https://github.com/Shiin-28/SideQuest.git
   ```
3. Open phpMyAdmin at http://localhost/phpmyadmin.
4. Go to the **Import** tab, choose `sidequestdb.sql`, and click **Import**. The file creates the `sidequestdb` database by itself, so you don't need to make it first.
5. Open http://localhost/SideQuest/SideQuest.php in your browser. You should see **Connection Successful!**

## Database connection settings

`connectscript.php` uses XAMPP's default login:

```php
$host = "localhost";
$user = 'root';
$pass = '';
$dbTARGET = 'sidequestdb';
```

If your MySQL uses a different username or password, change these values.
