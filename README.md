#                                                 Xavier
##                                             SQL Portfolio
### Welcome to my SQL Portfolio! This code repository contains examples of SQL I've written. Feel free to take a look and reach out if you have any questions.

## Climate Conference Analysis

### Project Overview
This project explores a climate conference database using SQL. The database includes information about VIP members, hotel reservations, and conference-related records.

### Database Tables
- VIPs
- Reservations
- Hotels

### SQL Skills Demonstrated
- SELECT statements
- Filtering and sorting data
- INNER JOIN
- Combining information from multiple tables
- Exploring relationships between database tables

### Project Purpose
The goal of this project is to practice using SQL to retrieve and analyze related information from a relational database.

### Tools Used
- SQL
- SQLite

SQL Example 1: LEFT JOIN — VIP Reservations

Business question: How can we view all VIP members and their reservation details, including members without reservations?

SELECT
    vips.first_name,
    vips.last_name,
    reservations.hotel,
    reservations.welcome_rsvp,
    reservations.dinner_rsvp
FROM vips
LEFT JOIN reservations
    ON vips.member_id = reservations.member_id;

What I learned:

- Used "LEFT JOIN" to retain all VIP records.
- Matched VIPs and reservations using "member_id".
- Identified VIPs without matching reservation records through NULL values.

Result: The query returned all 30 VIP records, including members without matching reservations.
