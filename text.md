Selezionare tutti gli studenti nati nel 1990 (160)

SELECT `date_of_birth` FROM `students` WHERE `date_of_birth` BETWEEN '1990-01-01' AND'1990-12-31';


"dopo aver selezionato le date di nascita degli studenti setto la ricerca tra il primo giorno del 1990 e l'ultimo giorno del 1990"
--------------------------------------------------

Selezionare tutti i corsi che valgono più di 10 crediti (479)

SELECT `cfu` FROM `courses` WHERE (`cfu`> 10);

"dopo aver selezionato cfu in corsi voglio vedere tutti i cfu > 10"
--------------------------------------------------

Selezionare tutti gli studenti che ad OGGI hanno almeno 30 anni compiuti (3725);

SELECT `date_of_birth` FROM `students` WHERE `date_of_birth` BETWEEN '1971-06-09' AND'1994-06-19'

"dopo aver selezionato le date di nascita degli studenti setto la ricerca dallo studente più anziano e chi compie i 30 anni oggi"
--------------------------------------------------

Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

SELECT * FROM `courses` WHERE(period = 'I semestre' AND year = 1);

"dopo aver selezionato tutto in corsi prendo tutti i period = 'I semestre' e year = 1"

"OCCHIO CHE '' E `` NON SONO UGUALI"
--------------------------------------------------

Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

SELECT * FROM `exams` WHERE (date = '2020/06/20' AND hour > '14:00:00');

"dopo aver selezionato tutto in esami prendo tutti gli appelli d'esame svolti dopo le 14 del 20-06-2020"
--------------------------------------------------

Selezionare tutti i corsi di laurea magistrale (38)

SELECT * FROM `degrees` WHERE(level = 'magistrale');

"dopo aver selezionato tutto in degrees prendo tutti i corsi di laurea di level = magistrale"
--------------------------------------------------

Da quanti dipartimenti è composta l'università? (12)

SELECT * FROM `departments`

"già selezionando tutto in dipartimenti ho anche il numero di dipartimenti"

SELECT `id` FROM `departments`;

"selezionando id in dipartimenti vedo solo il numero di dipartimenti"
--------------------------------------------------

Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

SELECT * FROM `teachers` WHERE (phone = 'NULL');
"NON VA BENE!"

SELECT * FROM `teachers` WHERE phone IS NULL;
"CORRETTO"
--------------------------------------------------

Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo degree_id, inserire un valore casuale)

clicco su SQL => SELECT * FROM `students` WHERE 1 => INSERISCI => Riempio i campi => esegui.

"controllo su lista studenti" 

SELECT * FROM `students` WHERE( surname = 'Calonaci');


id
degree_id
name
surname
date_of_birth
fiscal_code
enrolment_date
registration_number
email
	

5004
11
Matteo
Calonaci
1994-10-08
CLNMTT
2024-06-11
matteo.ca@prova.com
--------------------------------------------------

Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

SELECT * FROM `teachers` WHERE(surname = 'Rizzo');

UPDATE `teachers` SET `office_number` = '777' WHERE `teachers`.`id` = 58;
--------------------------------------------------

Eliminare dalla tabella studenti il record creato precedentemente al punto 9

DELETE FROM `students` WHERE `students`.`id` = 9;

--------------------------------------------------