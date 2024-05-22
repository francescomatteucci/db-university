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

-----SIXTH QUERY-----

SELECT `*`
FROM `degrees`
WHERE `name` LIKE 'Corso di Laurea Magistrale%';
 AND `date` = '2020-06-20';

-----SEVENTH QUERY-----

SELECT * FROM `departments`;

-----EIGHTH QUERY-----

SELECT `*`
FROM `teachers`
WHERE `phone` IS NULL;





--------QUERY WITH GROUP BY----------
1st query

SELECT YEAR(enrolment_date) AS anno, COUNT(id) AS numero_iscritti
FROM students
GROUP BY YEAR(enrolment_date)
ORDER BY anno;


2nd query

SELECT office_address, COUNT(id) AS numero_insegnanti
FROM teachers
GROUP BY office_address
ORDER BY numero_insegnanti DESC;

3rd query

SELECT exam_id, AVG(vote) AS media_voti
FROM exam_student
GROUP BY exam_id;

4th query

SELECT department_id, COUNT(name) AS numero_corsi
FROM degrees
GROUP BY department_id;



-------QUERY WITH JOIN---------

1st query

SELECT students.*
FROM students
JOIN degrees ON students.degree_id = degrees.id
WHERE degrees.name = 'Corso di Laurea in Economia';


2nd query

SELECT *
FROM degrees
JOIN departments ON degrees.department_id = departments.id
WHERE departments.name = 'Dipartimento di Neuroscienze' AND level = 'magistrale';

3rd query

SELECT courses.*
FROM courses
JOIN course_teacher ON courses.id = course_teacher.course_id
WHERE course_teacher.teacher_id = 44;


4th query


select students.*, degrees.*
from students, degrees, departments
where students.degree_id=degrees.id and degrees.department_id=departments.id
order by students.surname, students.name