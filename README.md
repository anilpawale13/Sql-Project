# Sql-Project

CREATE DATABASE FIT_TRACK_GYM;
USE FIT_TRACK_GYM;


-- CREATE TABLE 1) Members

CREATE TABLE Members (
    member_id INT  PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    equipment_id INT NOT NULL ,
	FOREIGN KEY (equipment_id) REFERENCES equipment(equipment_id)

);


INSERT INTO Members (member_id, first_name, last_name, email, equipment_id) VALUES
(1, 'John', 'Doe', 'john.doe@example.com', 1),
(2, 'Jane', 'Smith', 'jane.smith@example.com', 3),
(3, 'Michael', 'Johnson', 'michael.johnson@example.com', 5),
(4, 'Emily', 'Davis', 'emily.davis@example.com', 2),
(5, 'Daniel', 'Garcia', 'daniel.garcia@example.com', 6),
(6, 'Sarah', 'Martinez', 'sarah.martinez@example.com', 7),
(7, 'David', 'Lopez', 'david.lopez@example.com', 8),
(8, 'Laura', 'Gonzalez', 'laura.gonzalez@example.com', 9),
(9, 'James', 'Wilson', 'james.wilson@example.com', 10),
(10, 'Olivia', 'Lee', 'olivia.lee@example.com', 12),
(11, 'Matthew', 'Anderson', 'matthew.anderson@example.com', 13),
(12, 'Sophia', 'Thomas', 'sophia.thomas@example.com', 11),
(13, 'Joshua', 'Moore', 'joshua.moore@example.com', 15),
(14, 'Ava', 'Taylor', 'ava.taylor@example.com', 25),
(15, 'Christopher', 'Harris', 'christopher.harris@example.com', 24),
(16, 'Isabella', 'Clark', 'isabella.clark@example.com', 20),
(17, 'Ryan', 'Martinez', 'ryan.martinez@example.com', 19),
(18, 'Mia', 'Rodriguez', 'mia.rodriguez@example.com', 18),
(19, 'Andrew', 'Lewis', 'andrew.lewis@example.com', 4),
(20, 'Charlotte', 'Walker', 'charlotte.walker@example.com', 22),
(21, 'Joseph', 'Hall', 'joseph.hall@example.com', 17),
(22, 'Ella', 'Allen', 'ella.allen@example.com',10),
(23, 'Benjamin', 'Young', 'benjamin.young@example.com', 21),
(24, 'Liam', 'King', 'liam.king@example.com', 18),
(25, 'Mason', 'Wright', 'mason.wright@example.com',23);








select * from Members;





-- CREATE TABLE 1) Members
--  -------------------------------------------------

-- CREATE TABLE 2) Trainers


CREATE TABLE Trainers (
    trainer_id INT  PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    specialization VARCHAR(50),
    equipment_id INT NOT NULL ,
        FOREIGN KEY (equipment_id) REFERENCES equipment(equipment_id)
);
INSERT INTO Trainers (trainer_id, first_name, last_name, specialization,equipment_id) VALUES
(1, 'Alex', 'Thompson', 'Yoga', 8),
(2, 'Sophia', 'Hernandez', 'Cardio', 14),
(3, 'Ethan', 'Miller', 'Strength Training', 16),
(4, 'Ava', 'Davis', 'Pilates', 13),
(5, 'Liam', 'Martinez', 'CrossFit', 7),
(6, 'Olivia', 'Garcia', 'Aerobics', 22),
(7, 'Noah', 'Rodriguez', 'Bodybuilding', 8),
(8, 'Mia', 'Wilson', 'Zumba', 5),
(9, 'Lucas', 'Anderson', 'Kickboxing', 14),
(10, 'Isabella', 'Taylor', 'Personal Training', 16),
(11, 'Mason', 'Thomas', 'HIIT', 13),
(12, 'Emma', 'Jackson', 'Functional Training', 17),
(13, 'Elijah', 'White', 'Cycling',25),
(14, 'Charlotte', 'Harris', 'Dance Fitness', 20),
(15, 'Oliver', 'Clark', 'Strength and Conditioning', 19),
(16, 'Amelia', 'Lewis', 'Boxing', 18),
(17, 'James', 'Robinson', 'Sports Conditioning', 15),
(18, 'Harper', 'Walker', 'Core Training', 7),
(19, 'Benjamin', 'Young', 'Flexibility Training', 12),
(20, 'Evelyn', 'King', 'TRX', 23),
(21, 'Lucas', 'Scott', 'Mixed Martial Arts', 6),
(22, 'Ella', 'Green', 'Circuit Training', 24),
(23, 'Jackson', 'Adams', 'Athletic Performance', 10),
(24, 'Grace', 'Baker', 'Rehabilitation', 3),
(25, 'Henry', 'Gonzalez', 'Outdoor Training', 6);


SELECT * FROM Trainers;




-- CREATE TABLE 2) Trainers

--  -------------------------------------------------


-- CREATE TABLE 2) Classes 

CREATE TABLE Classes (
    class_id INT PRIMARY KEY,
    class_name VARCHAR(100) NOT NULL,
    trainer_id INT,
    class_date DATE NOT NULL,
    duration_minutes INT NOT NULL,
    FOREIGN KEY (trainer_id) REFERENCES Trainers(trainer_id)
);
INSERT INTO Classes (class_id, class_name, trainer_id, class_date, duration_minutes) VALUES
(1, 'Morning Yoga', 1, '2024-08-01', 60),
(2, 'Cardio Blast', 2, '2024-08-02', 45),
(3, 'Strength Circuit', 3, '2024-08-03', 50),
(4, 'Pilates Mat', 4, '2024-08-04', 60),
(5, 'CrossFit Essentials', 5, '2024-08-05', 55),
(6, 'Aerobics for Beginners', 6, '2024-08-06', 45),
(7, 'Advanced Bodybuilding', 7, '2024-08-07', 75),
(8, 'Zumba Dance', 8, '2024-08-08', 50),
(9, 'Kickboxing Basics', 9, '2024-08-09', 60),
(10, 'Personal Training Session', 10, '2024-08-10', 30),
(11, 'HIIT Workout', 11, '2024-08-11', 40),
(12, 'Functional Training', 12, '2024-08-12', 60),
(13, 'Indoor Cycling', 13, '2024-08-13', 45),
(14, 'Dance Fitness', 14, '2024-08-14', 50),
(15, 'Strength and Conditioning', 15, '2024-08-15', 60),
(16, 'Boxing Drills', 16, '2024-08-16', 70),
(17, 'Sports Conditioning', 17, '2024-08-17', 55),
(18, 'Core Stability', 18, '2024-08-18', 45),
(19, 'Flexibility Training', 19, '2024-08-19', 40),
(20, 'TRX Suspension Training', 20, '2024-08-20', 50),
(21, 'MMA Techniques', 21, '2024-08-21', 60),
(22, 'Circuit Training', 22, '2024-08-22', 45),
(23, 'Athletic Performance', 23, '2024-08-23', 55),
(24, 'Rehabilitation Exercises', 24, '2024-08-24', 40),
(25, 'Outdoor Training', 25, '2024-08-25', 60);



SELECT * FROM Classes;


-- CREATE TABLE 2) CLASSES

--  -------------------------------------------------



-- CREATE TABLE 2) Equipment


CREATE TABLE Equipment (
    equipment_id INT PRIMARY KEY,
    equipment_name VARCHAR(100) NOT NULL,
    equipment_type VARCHAR(50) NOT NULL,
    purchase_date DATE NOT NULL,
    maintenance_date DATE
);
INSERT INTO Equipment (equipment_id, equipment_name, equipment_type, purchase_date, maintenance_date) VALUES
(1, 'Treadmill', 'Cardio', '2022-01-15', '2024-07-01'),
(2, 'Elliptical', 'Cardio', '2021-06-10', '2024-06-10'),
(3, 'Stationary Bike', 'Cardio', '2021-12-05', '2024-07-15'),
(4, 'Rowing Machine', 'Cardio', '2022-03-22', '2024-07-22'),
(5, 'Bench Press', 'Strength', '2021-04-18', '2024-05-18'),
(6, 'Dumbbells Set', 'Strength', '2020-08-25', '2024-08-25'),
(7, 'Kettlebells Set', 'Strength', '2022-02-14', '2024-07-30'),
(8, 'Leg Press Machine', 'Strength', '2021-09-30', '2024-07-10'),
(9, 'Squat Rack', 'Strength', '2021-05-11', '2024-05-11'),
(10, 'Pull-up Bar', 'Bodyweight', '2022-06-01', '2024-06-01'),
(11, 'TRX Straps', 'Functional', '2020-12-20', '2024-07-25'),
(12, 'Yoga Mats', 'Flexibility', '2021-03-03', '2024-08-03'),
(13, 'Resistance Bands', 'Functional', '2022-05-17', '2024-07-05'),
(14, 'Medicine Balls', 'Functional', '2021-07-22', '2024-07-22'),
(15, 'Barbells', 'Strength', '2020-11-30', '2024-11-30'),
(16, 'Plyo Boxes', 'Plyometrics', '2021-08-10', '2024-08-10'),
(17, 'Battle Ropes', 'Cardio', '2021-10-05', '2024-10-05'),
(18, 'Foam Rollers', 'Recovery', '2022-04-25', '2024-07-20'),
(19, 'Cable Machine', 'Strength', '2021-01-12', '2024-01-12'),
(20, 'Smith Machine', 'Strength', '2020-09-18', '2024-09-18'),
(21, 'Jump Ropes', 'Cardio', '2022-07-07', '2024-07-07'),
(22, 'Punching Bag', 'Boxing', '2021-11-21', '2024-11-21'),
(23, 'Spin Bikes', 'Cardio', '2020-10-15', '2024-10-15'),
(24, 'Rowers', 'Cardio', '2021-02-28', '2024-08-01'),
(25, 'Sandbags', 'Functional', '2022-08-12', '2024-08-12');



SELECT * FROM Equipment;


-- CREATE TABLE 2) Equipment

--  -------------------------------------------------


-- CREATE TABLE 2)  Memberships
CREATE TABLE Memberships (
    membership_id INT PRIMARY KEY,
    member_id INT,
    start_date DATE NOT NULL,
    end_date DATE NOT NULL,
    membership_type VARCHAR(50) NOT NULL,
    
    FOREIGN KEY (member_id) REFERENCES Members(member_id)
);

INSERT INTO Memberships (membership_id, member_id, start_date, end_date, membership_type) VALUES
(1, 1, '2024-01-01', '2024-12-31', 'Standard'),
(2, 2, '2024-02-01', '2024-12-31', 'Premium'),
(3, 3, '2024-03-01', '2024-12-31', 'Basic'),
(4, 4, '2024-04-01', '2024-12-31', 'Standard'),
(5, 5, '2024-05-01', '2024-12-31', 'Premium'),
(6, 6, '2024-06-01', '2024-12-31', 'Basic'),
(7, 7, '2024-07-01', '2024-12-31', 'Standard'),
(8, 8, '2024-08-01', '2024-12-31', 'Premium'),
(9, 9, '2024-09-01', '2024-12-31', 'Basic'),
(10, 10, '2024-10-01', '2024-12-31', 'Standard'),
(11, 11, '2024-11-01', '2024-12-31', 'Premium'),
(12, 12, '2024-01-01', '2024-12-31', 'Basic'),
(13, 13, '2024-02-01', '2024-12-31', 'Standard'),
(14, 14, '2024-03-01', '2024-12-31', 'Premium'),
(15, 15, '2024-04-01', '2024-12-31', 'Basic'),
(16, 16, '2024-05-01', '2024-12-31', 'Standard'),
(17, 17, '2024-06-01', '2024-12-31', 'Premium'),
(18, 18, '2024-07-01', '2024-12-31', 'Basic'),
(19, 19, '2024-08-01', '2024-12-31', 'Standard'),
(20, 20, '2024-09-01', '2024-12-31', 'Premium'),
(21, 21, '2024-10-01', '2024-12-31', 'Basic'),
(22, 22, '2024-11-01', '2024-12-31', 'Standard'),
(23, 23, '2024-01-01', '2024-12-31', 'Premium'),
(24, 24, '2024-02-01', '2024-12-31', 'Basic'),
(25, 25, '2024-03-01', '2024-12-31', 'Standard');

SELECT * FROM  Memberships;

-- CREATE TABLE 2)  Memberships

-  -------------------------------------------------


-- CREATE TABLE 2)  Bookings



CREATE TABLE Bookings (
    booking_id INT PRIMARY KEY,
    member_id INT,
    class_id INT,
    booking_date DATE NOT NULL,
    booking_type varchar(50) not null,
   status VARCHAR(20) NOT NULL,
    
    FOREIGN KEY (member_id) REFERENCES Members(member_id),
    FOREIGN KEY (class_id) REFERENCES Classes(class_id)
);
INSERT INTO Bookings (booking_id, member_id, class_id, booking_date,booking_type, status) VALUES
(1, 1, 1, '2024-07-01','Gold','Confirmed'),
(2, 2, 2, '2024-07-01','Gold','Cancelled'),
(3, 3, 3, '2024-07-02', 'Platinum','Confirmed'),
(4, 4, 4, '2024-07-02','Silver','Confirmed'),
(5, 5, 5, '2024-07-03','Silver','Pending'),
(6, 6, 6, '2024-07-03', 'Platinum','Confirmed'),
(7, 7, 7, '2024-07-04','Gold','Cancelled'),
(8, 8, 8, '2024-07-04','Silver','Confirmed'),
(9, 9, 9, '2024-07-05','Platinum','Pending'),
(10, 10, 10, '2024-07-05','Silver','Confirmed'),
(11, 11, 11, '2024-07-06','Gold','Confirmed'),
(12, 12, 12, '2024-07-06','Gold','Cancelled'),
(13, 13, 13, '2024-07-07','Gold','Pending'),
(14, 14, 14, '2024-07-07','Silver','Confirmed'),
(15, 15, 15, '2024-07-08','Platinum','Confirmed'),
(16, 16, 16, '2024-07-08','Gold','Pending'),
(17, 17, 17, '2024-07-09','Silver','Cancelled'),
(18, 18, 18, '2024-07-09','Silver','Confirmed'),
(19, 19, 19, '2024-07-10','Gold','Confirmed'),
(20, 20, 20, '2024-07-10',' Platinum','Pending'),
(21, 21, 21, '2024-07-11', 'Silver','Cancelled'),
(22, 22, 22, '2024-07-11', 'Gold','Confirmed'),
(23, 23, 23, '2024-07-12','Platinum','Pending'),
(24, 24, 24, '2024-07-12','Gold' ,'Confirmed'),
(25, 25, 25, '2024-07-13','Silver' ,'Confirmed');

SELECT * FROM  Bookings;

desc equipment;

-- CREATE TABLE 2)  Bookings

-  -------------------------------------------------













-- This subquery most recent booking date for each member.

SELECT member_id, MAX(booking_date) AS most_recent_booking
FROM Bookings
GROUP BY member_id;

-- This subquery lists all classes that have not had any bookings with the status 'Confirmed'.



-- MULTPLE SUBQUERY


-- Example 1: Finding Members with the Most Bookings
-- This query identifies the top 5 members who have booked the most classes.


SELECT 
    m.member_id,
    m.first_name,
    m.last_name,
    COUNT(b.booking_id) AS total_bookings
FROM 
    Members m
JOIN 
    Bookings b ON m.member_id = b.member_id
GROUP BY 
    m.member_id, m.first_name, m.last_name
ORDER BY 
    total_bookings DESC
LIMIT 5;


-- This query finds classes that have not been booked by any members.

SELECT 
    c.class_id,
    c.class_name,
    c.class_date,
    c.duration_minutes
FROM 
    Classes c
LEFT JOIN 
    Bookings b ON c.class_id = b.class_id
WHERE 
    b.booking_id IS NULL;
    
 ------------------------   
SELECT 
    Members.first_name,
    Members.last_name,
    Classes.class_name,
    Bookings.booking_date,
    Bookings.status
FROM 
    Bookings
INNER JOIN 
    Members ON Bookings.member_id = Members.member_id
INNER JOIN 
    Classes ON Bookings.class_id = Classes.class_id;
    
    
    
    
-- 1. Find Members Who Have Booked Classes
-- Purpose: To get a list of members who have booked at least one class, along with the class details and their booking status.(done)

    SELECT 
    Members.first_name,
    Bookings.status
FROM 
    Members
INNER JOIN 
    Bookings ON Members.member_id = Bookings.member_id;
    
    
    
-- INNER JOIN 
 --   Classes ON Bookings.class_id = Classes.class_id;


-- 
-- List All Classes and the Number of Members Booked (done)

SELECT 
    Classes.class_name,
    COUNT(Bookings.member_id) AS number_of_bookings
FROM 
    Classes
LEFT JOIN 
    Bookings ON Classes.class_id = Bookings.class_id
GROUP BY 
    Classes.class_name;
    
    -- -----------------------
    
SELECT 
    Trainers.first_name,
    Trainers.specialization,
    Classes.class_name,
    Classes.class_date
FROM 
    Classes
RIGHT JOIN 
    Trainers ON Classes.trainer_id = Trainers.trainer_id;

    
    
    -- --------------------------
    
    CREATE VIEW Gold_MemberBookingsView AS
SELECT 
    m.first_name,
    m.last_name,
    b.booking_id,
    b.booking_date,
    b.status,
    b.booking_type
FROM 
    Member m
INNER JOIN 
    Bookings b ON m.member_id = b.member_id
INNER JOIN 
    Memberships ms ON m.member_id = ms.member_id
WHERE 
    ms.membership_type = 'Gold';
    
    
select * from GoldMemberBookingsView;

CREATE VIEW MemberClassBookings AS
SELECT 
    m.first_name,
    m.last_name,
    c.class_name
FROM 
    Members m
INNER JOIN 
    Bookings b ON m.member_id = b.member_id
INNER JOIN 
    Classes c ON b.class_id = c.class_id;
    
select * from MemberClassBookings;

    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    

 
    
    
    
    
    
    
    
    
    
    
    
    
    DESCRIBE Members;
    Desc Members;
    
    
 
 
 
    
DESCRIBE Bookings;
    
    
    
    
    
    
    
SELECT Members.first_name, Classes.class_name, Bookings.booking_date
FROM Members
INNER JOIN Bookings ON Members.member_id = Bookings.member_id
INNER JOIN Classes ON Bookings.class_id = Classes.class_id
WHERE Bookings.status = 'Confirmed';







-- -----------------------
CREATE VIEW Active_Members AS
SELECT 
    m.member_id,
    m.first_name,
   ms.membership_type,
    ms.start_date,
    ms.end_date
FROM 
    Members m
INNER JOIN 
    Memberships ms ON m.member_id = ms.member_id
WHERE 
    ms.end_date >= CURDATE();
    
    select * from Active_Members;

-- ---------------------

-- --------------------

CREATE VIEW ClassAttendance AS
SELECT 
    c.class_id,
    c.class_name,
    c.class_date,
    COUNT(b.booking_id) AS number_of_attendees,
    COUNT(CASE WHEN b.status = 'Confirmed' THEN 1 END) AS confirmed_attendees,
    COUNT(CASE WHEN b.status = 'Cancelled' THEN 1 END) AS cancelled_attendees
FROM 
    Classes c
LEFT JOIN 
    Bookings b ON c.class_id = b.class_id
GROUP BY 
    c.class_id, c.class_name, c.class_date;


-- --------------------



-- -------------------------

CREATE VIEW EquipmentUsage AS
SELECT 
    e.equipment_id,
    e.equipment_name,
    e.equipment_type,
    
    MAX(e.maintenance_date) AS last_maintenance_date
FROM 
    Equipment e
LEFT JOIN 
    Bookings b ON e.equipment_id = b.booking_id
GROUP BY 
    e.equipment_id, e.equipment_name, e.equipment_type;
    
    select * from EquipmentUsage;

-- -------------------------

-- -----------------
SELECT member_id, first_name,last_name FROM Members
WHERE member_id = ANY (SELECT b.member_id FROM Bookings b WHERE b.class_id = ANY (
	SELECT class_id FROM Bookings GROUP BY class_id HAVING 
	COUNT(DISTINCT member_id) < (SELECT COUNT(member_id) FROM Members)));


-- ------------------

-- ----------------

-- Find the names of members who have booked any class on the same date as the 'Zumba Dance' class.

SELECT first_name, last_name
FROM Members
WHERE member_id IN (
    SELECT member_id
    FROM Bookings
    WHERE booking_date = (SELECT booking_date FROM Classes WHERE class_name = 'Zumba Dance')
);

-- ----------------

-- -----------------

-- Find the email addresses of members who have booked the class 'Morning Yoga'.

SELECT email
FROM Members
WHERE member_id IN (SELECT member_id FROM Bookings WHERE class_id =
(SELECT class_id FROM Classes WHERE class_name = 'Morning Yoga'));

-- -----------------

-- -----------------

-- Find the names of trainers who have conducted classes with less than 5 bookings.

SELECT first_name, last_name
FROM Trainers
WHERE trainer_id IN (SELECT trainer_id FROM Classes WHERE class_id IN 
(SELECT class_id FROM Bookings GROUP BY class_id HAVING COUNT(booking_id) < 5));

-- ----------------

-- ---------------
-- Find members who have booked a specific class (e.g., 'Morning Yoga')

SELECT first_name, last_name
FROM Members
WHERE member_id IN (SELECT member_id FROM Bookings WHERE class_id = 1);

-- ---------------
