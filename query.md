SELECT * FROM `students` WHERE `date_of_birth` LIKE '1990%';

SELECT * FROM `courses` WHERE `cfu` > 10;

SELECT * FROM `students` WHERE `date_of_birth` < "1993-10-17";

SELECT * FROM `courses` WHERE `year` = 1 AND `period`= "I semestre";

SELECT * FROM `exams` WHERE `date` = "2020-06-20" AND `hour` > "14:00";

SELECT * FROM `degrees` WHERE `level` = "magistrale";

SELECT COUNT(*) FROM departments;

SELECT * FROM `teachers` WHERE `phone` IS NULL;




<!-- Group by:  -->

<!-- Contare quanti iscritti ci sono stati ogni anno -->

<!-- Contare gli insegnanti che hanno l'ufficio nello stesso edificio -->
SELECT count(*), office_number FROM `teachers` group by `office_number`;

<!-- Calcolare la media dei voti di ogni appello d'esame -->
SELECT AVG(vote) FROM `exam_student` WHERE `vote`; 

<!-- Contare quanti corsi di laurea ci sono per ogni dipartimento -->
SELECT COUNT(*), department_id FROM `degrees` GROUP BY `department_id`;


<!-- Joins: -->

<!-- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia -->
SELECT * FROM `students` LEFT JOIN degrees ON students.degree_id = degrees.id WHERE degrees.name = 'Corso di Laurea in Economia'; 

<!-- Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze -->
SELECT * FROM `courses` LEFT JOIN degrees ON courses.degree_id = degrees.id left join departments on degrees.department_id = departments.id where degrees.level = 'magistrale' and departments.name = 'Dipartimento di Neuroscienze';

<!-- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44) -->

<!-- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome -->
<!-- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti -->
<!-- Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54) -->
<!-- BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.  -->