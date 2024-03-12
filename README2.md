## Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT \*
FROM students
WHERE degree_id IN (SELECT id FROM degrees WHERE name = 'Economia');

## Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

SELECT \*
FROM degrees
WHERE level = 'Magistrale' AND department_id = (SELECT id FROM departments WHERE name = 'Neuroscienze');

## Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT c.\*
FROM courses c
JOIN teachings t ON c.id = t.course_id
JOIN teachers te ON t.teacher_id = te.id
WHERE te.name = 'Fulvio' AND te.surname = 'Amato';

## Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

SELECT s.name, s.surname, d.name AS degree_name, dp.name AS department_name
FROM students s
JOIN degrees d ON s.degree_id = d.id
JOIN departments dp ON d.department_id = dp.id
ORDER BY s.surname, s.name;

## Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

SELECT d.name AS degree_name, c.name AS course_name, t.name AS teacher_name, t.surname AS teacher_surname
FROM degrees d
JOIN courses c ON d.id = c.degree_id
JOIN teachings ts ON c.id = ts.course_id
JOIN teachers t ON ts.teacher_id = t.id;

## Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

SELECT t.\*
FROM teachers t
JOIN departments d ON t.department_id = d.id
WHERE d.name = 'Matematica';
