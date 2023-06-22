---
sidebar_position: 2
---

# Installation

Before installing the script please make sure you run the following dependencies :
- `es_extended` (version 1.4.0 or above)
- `oxmysql`

## SQL Schema

Firstable you will need to apply the following SQL requests in order to install the script.

```sql title="schema.sql"
DROP TABLE IF EXISTS `red_reports`;
CREATE TABLE `red_reports` (
    `id` int(11) AUTO_INCREMENT PRIMARY KEY,
    `caller` varchar(255) NOT NULL,
    `message` varchar(255) NOT NULL,
    `date` datetime NOT NULL,
    `solved` int(1) NOT NULL DEFAULT 0,
    `dateSolved` datetime DEFAULT NULL,
    `assignedTo` varchar(255) NOT NULL DEFAULT ''
);

DROP TABLE IF EXISTS `red_reports_messages`;
CREATE TABLE `red_reports_messages` (
    `id` int(11) AUTO_INCREMENT PRIMARY KEY,
    `reportId` int(11) NOT NULL,
    `content` text NOT NULL,
    `sender` varchar(46) NOT NULL,
    `sentat` DATETIME NOT NULL
);

DROP TABLE IF EXISTS `red_notes`;
CREATE TABLE `red_notes` (
  `id` int(11) NOT NULL AUTO_INCREMENT PRIMARY KEY,
  `identifier` varchar(46) NOT NULL,
  `sender` varchar(46) NOT NULL,
  `content` text NOT NULL,
  `date` datetime NOT NULL,
  `type` INT(1) NOT NULL DEFAULT '0'
);

DROP TABLE IF EXISTS `red_bans`;
CREATE TABLE `red_bans` (
  `id` int(11) AUTO_INCREMENT PRIMARY KEY,
  `banner` varchar(46) NOT NULL,
  `player` varchar(46) NOT NULL,
  `date_banned` datetime NOT NULL,
  `banned_until` datetime NOT NULL,
  `reason` varchar(100) NOT NULL
);

DROP TABLE IF EXISTS `red_settings`;
CREATE TABLE `red_settings` (
  `identifier` varchar(100) NOT NULL PRIMARY KEY,
  `ratio` float(6) NOT NULL,
  `color` varchar(10) NOT NULL,
  `sidebar` tinyint(1) NOT NULL,
  `onduty` tinyint(1) NOT NULL
);

DROP TABLE IF EXISTS `red_logins`;
CREATE TABLE `red_logins` (
  `id` int(11) AUTO_INCREMENT PRIMARY KEY,
  `identifier` varchar(46) NOT NULL,
  `date` datetime NOT NULL
);
```

### phpMyAdmin

#### SQL command input
![PMA SQL](/img/sql/pma-sql.png)

#### Importing file
![PMA SQL](/img/sql/pma-import.png)

### CLI
```shell-session
$ mysql -u username -p database_name < schema.sql
``` 