## Contare quanti iscritti ci sono stati ogni anno

SELECT YEAR(enrolment_date) AS Anno, COUNT(\*) AS Numero_Iscritti
FROM students
GROUP BY YEAR(enrolment_date);

## Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT office_address, COUNT(\*) AS Numero_Insegnanti
FROM teachers
GROUP BY office_address;

## Calcolare la media dei voti di ogni appello d'esame

SELECT e.id AS id_appello, AVG(v.grade) AS Media_Voti
FROM exams e
JOIN vote v ON e.id = v.exam_id
GROUP BY e.id;

## Contare quanti corsi di laurea ci sono per ogni dipartimento

SELECT department_id, COUNT(\*) AS Numero_Corsi
FROM degrees
GROUP BY department_id;
