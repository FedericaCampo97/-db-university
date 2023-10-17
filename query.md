SELECT * FROM `students` WHERE `date_of_birth` LIKE '1990%';

SELECT * FROM `courses` WHERE `cfu` > 10;

SELECT * FROM `students` WHERE `date_of_birth` < "1993-10-17";

SELECT * FROM `courses` WHERE `year` = 1 AND `period`= "I semestre";

SELECT * FROM `exams` WHERE `date` = "2020-06-20" AND `hour` > "14:00";

SELECT * FROM `degrees` WHERE `level` = "magistrale";

SELECT COUNT(*) FROM departments;

SELECT * FROM `teachers` WHERE `phone` IS NULL;