1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT students.id, students.name, students.surname, degrees.name
FROM students
INNER JOIN degrees ON students.id = degrees.id

=> 100
--------------------------------------------------

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
Neuroscienze

SELECT degrees.name, degrees.level, departments.name 
FROM departments 
INNER JOIN degrees ON departments.id = degrees.id 
WHERE(degrees.level = 'magistrale' AND departments.name = 'Dipartimento di Neuroscienze');

=> 1
--------------------------------------------------

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT teachers.name, teachers.surname, courses.name AS nome_corso 
FROM teachers 
INNER JOIN course_teacher ON course_teacher.teacher_id = teachers.id 
INNER JOIN courses ON course_teacher.course_id = courses.id 
WHERE teachers.name = 'Fulvio' AND teachers.surname = 'Amato';

=> 11
--------------------------------------------------

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
nome

SELECT students.name, students.surname, degrees.name,departments.name 
FROM `students` 
INNER JOIN degrees ON students.id = degrees.id 
INNER JOIN departments ON students.id = departments.id 
ORDER BY students.surname, students.name ASC;

=> 12
--------------------------------------------------

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

SELECT degrees.name AS Corso_di_Laurea, courses.name AS Corso, teachers.name AS Nome, teachers.surname AS Cognome 
FROM degrees 
INNER JOIN courses ON degrees.id = courses.id 
INNER JOIN teachers ON degrees.id = teachers.id;

=> 75
--------------------------------------------------

6. Selezionare tutti i docenti che insegnano nel Dipartimento di
Matematica (54)

SELECT DISTINCT  teachers.name AS Nome, teachers.surname AS Cognome, departments.name AS Nome_Dipartimento 
FROM departments
INNER JOIN degrees ON degrees.department_id = departments.id
INNER JOIN courses ON courses.degree_id = degrees.id
INNER JOIN course_teacher ON course_teacher.course_id = courses.id
INNER JOIN teachers ON course_teacher.teacher_id = teachers.id
WHERE( departments.name = 'Dipartimento di Matematica');

=> 70 con l'aggiunta di DISTRICT => 54
--------------------------------------------------

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
per ogni esame, stampando anche il voto massimo. Successivamente,
filtrare i tentativi con voto minimo 18.
--------------------------------------------------
