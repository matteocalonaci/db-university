1. Contare quanti iscritti ci sono stati ogni anno

SELECT enrolment_date AS Data_iscrizione,
 COUNT(*) AS n_iscritti 
 FROM students 
 GROUP BY enrolment_date;

--------------------------------------------------

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT office_address,
COUNT(*) AS n_teacher 
FROM `teachers` 
GROUP BY office_address 
ORDER BY n_teacher ASC;

--------------------------------------------------

3. Calcolare la media dei voti di ogni appello d'esame

SELECT exam_id AS Esame,
AVG(vote) AS Media_voto 
FROM `exam_student` 
GROUP BY Esame;
ORDER BY Media_voto DISC;

--------------------------------------------------

4. Contare quanti corsi di laurea ci sono per ogni dipartimento

SELECT department_id AS Corso_Laurea, name , 
COUNT(department_id) AS n_Corsi 
FROM `degrees` 
GROUP BY department_id;

--------------------------------------------------