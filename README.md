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

SQL Example 2: INNER JOIN — VIPs With Reservations

Business question: Which VIP members have reservation records?

SELECT
    vips.first_name,
    vips.last_name,
    reservations.hotel,
    reservations.welcome_rsvp
FROM vips
INNER JOIN reservations
    ON vips.member_id = reservations.member_id;

What it demonstrates:

- Used "INNER JOIN" to return VIPs with matching reservation records.
- Connected tables using "member_id".
- Retrieved hotel and welcome RSVP information.

Result: Returned 27 VIPs with matching reservations.

---

SQL Example 3: Multiple JOINs — VIPs and Hotel Details

Business question: Which hotels are VIP members staying at, and what are the reservation details?

SELECT
    vips.first_name,
    vips.last_name,
    hotels.hotel_name,
    hotels.address,
    reservations.welcome_rsvp,
    reservations.dinner_rsvp
FROM vips
INNER JOIN reservations
    ON vips.member_id = reservations.member_id
INNER JOIN hotels
    ON reservations.hotel = hotels.hotel_id;

What it demonstrates:

- Combined three related tables using multiple "INNER JOIN" statements.
- Connected VIPs to reservations and reservations to hotels.
- Retrieved hotel names, addresses, and RSVP information.

Result: Returned 27 matching VIP reservation records with hotel details.

---

SQL Example 4: Subquery — VIPs With Reservations

Business question: How can we find VIP members whose IDs appear in the reservations table?

SELECT
    first_name,
    last_name
FROM vips
WHERE member_id IN (
    SELECT member_id
    FROM reservations
);

What it demonstrates:

- Used a subquery to retrieve member IDs from the reservations table.
- Used "IN" to find VIP records matching those IDs.
- Practiced combining an inner query with an outer query.

Result: Returned 27 VIP members with reservation records.
