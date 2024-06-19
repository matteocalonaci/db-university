Selezionare tutti gli studenti nati nel 1990 (160)

SELECT `date_of_birth` FROM `students` WHERE `date_of_birth` BETWEEN '1990-01-01' AND'1990-12-31';
<!-- dopo aver selezionato le date di nascita degli studenti setto la ricerca tra il primo giorno del 1990 e l'ultimo giorno del 1990 -->
--------------------------------------------------

Selezionare tutti i corsi che valgono più di 10 crediti (479)

SELECT `cfu` FROM `courses` WHERE (`cfu`> 10);
<!-- dopo aver selezionato cfu in corsi voglio vedere tutti i cfu > 10 -->
--------------------------------------------------

Selezionare tutti gli studenti che ad OGGI hanno almeno 30 anni compiuti (3725)

SELECT `date_of_birth` FROM `students` WHERE `date_of_birth` BETWEEN '1971-06-09' AND'1994-06-19';
<!-- dopo aver selezionato le date di nascita degli studenti setto la ricerca dallo studente più anziano e chi compie i 30 anni oggi -->
--------------------------------------------------

Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

SELECT * FROM `courses` WHERE(period = 'I semestre' AND year = 1);
<!-- dopo aver selezionato tutto in corsi prendo tutti i period = 'I semestre' e year = 1 -->
<!-- OCCHIO CHE '' E `` NON SONO UGUALI -->
--------------------------------------------------

Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

SELECT * FROM `exams` WHERE (date = '2020/06/20' AND hour > '14:00:00');
<!-- dopo aver selezionato tutto in esami prendo tutti gli appelli d'esame svolti dopo le 14 del 20-06-2020 -->
--------------------------------------------------

Selezionare tutti i corsi di laurea magistrale (38)

SELECT * FROM `degrees` WHERE(level = 'magistrale');
<!-- dopo aver selezionato tutto in degrees prendo tutti i corsi di laurea di level = magistrale -->
--------------------------------------------------


