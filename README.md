# EX - Query con SELECT

## Selezionare tutti gli studenti nati nel 1990 (160)

SELECT \* FROM students WHERE YEAR(birth_date) = 1990;

## Selezionare tutti i corsi che valgono più di 10 crediti (479)

SELECT \* FROM courses WHERE credits > 10;

## Selezionare tutti gli studenti che hanno più di 30 anni

SELECT \* FROM students WHERE birth_date <= DATE_SUB(CURDATE(), INTERVAL 30 YEAR);

## Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

SELECT \* FROM courses WHERE year = 1 AND semester = 1;

## Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

SELECT \* FROM exams WHERE DATE(exam_date) = '2020-06-20' AND TIME(exam_date) > '14:00:00';

## Selezionare tutti i corsi di laurea magistrale (38)

SELECT \* FROM degrees WHERE type = 'Laurea Magistrale';

## Da quanti dipartimenti è composta l'università? (12)

SELECT COUNT(\*) FROM departments;

## Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

SELECT COUNT(\*) FROM teachers WHERE phone_number IS NULL;
