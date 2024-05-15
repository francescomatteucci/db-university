-----FIRST QUERY-----

SELECT (`*`)
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990;

-----SECOND QUERY-----

SELECT * FROM `courses` WHERE `cfu` > 10;


-----THIRD QUERY-----

SELECT `*`
FROM `students`
WHERE YEAR(`date_of_birth`) <= YEAR(CURRENT_DATE()) - 30;

-----FOURTH QUERY-----

SELECT `*`
FROM `courses`
WHERE `year` = 1 AND `period` LIKE 'I %';

-----FIFTH QUERY-----

SELECT `*`
FROM `exams`
WHERE `hour` >= '14%' AND `date` = '2020-06-20';