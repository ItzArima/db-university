1.

SELECT * FROM `students` WHERE date_of_birth BETWEEN '1990-1-1' AND '1990-12-31';


2.

SELECT * FROM `courses` WHERE cfu>10;


3.

SELECT * FROM `students` WHERE date_of_birth < '1991-12-14';


4.

SELECT * FROM `courses` WHERE   period = 'I semestre' AND year = 1;


5.

SELECT * FROM `exams` WHERE date = '2020-06-20' AND hour > '14:00:00';


6.

SELECT * FROM `degrees` WHERE level = 'magistrale';



7.

SELECTCOUNT(id) as 'total_departements_number' FROM  `departements`;


8.

SELECT * FROM `teachers` WHERE phone IS null;


