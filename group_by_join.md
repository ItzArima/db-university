GROUP BY

1.

SELECT COUNT(id) AS `total_registrations` , year(`enrolment_date`) AS `year`
FROM `students`
GROUP BY year(`enrolment_date`);

2.

SELECT COUNT(id) AS `total_teachers` , `office_address` AS `address`
FROM `teachers`
GROUP BY `office_address`;

3.

SELECT ROUND(AVG(`vote`)) AS `vote_average`, `exam_id`
FROM `exam_student`
GROUP BY `exam_id`;

4.

SELECT COUNT(id) AS `total_courses` , `department_id`
FROM `degrees`
GROUP BY `department_id`;


JOIN

1.

SELECT students.name , students.surname
FROM `degrees`
JOIN `students`
ON students.degree_id = degrees.id
WHERE degrees.name = 'Corso di Laurea in Economia'

2.

SELECT *
FROM `degrees`
JOIN `departments`
ON degrees.department_id = departments.id
WHERE departments.name = 'Dipartimento di Neuroscienze'

3.

SELECT * FROM `courses`
JOIN `course_teacher`
ON courses.id = course_teacher.course_id
WHERE course_teacher.teacher_id = 44

4.

SELECT  students.name , students.surname , degrees.name , departments.name
FROM `students`
JOIN `degrees`
ON students.degree_id = degrees.id
JOIN `departments`
ON degrees.id = departments.id
ORDER BY students.surname;

5.

SELECT degrees.name as `nome_corso_di_laurea`, degrees.address as `indirizzo` , courses.name as `nome_corso`, teachers.name as `nome_insegnante`, teachers.surname as `cognome_insegnate`
FROM `degrees`
JOIN `courses`
ON degrees.id = courses.degree_id
JOIN `course_teacher`
ON courses.id = course_teacher.course_id
JOIN `teachers`
ON course_teacher.teacher_id = teachers.id
ORDER BY degrees.name;

6.

SELECT teachers.name , teachers.surname
FROM `teachers`
JOIN `course_teacher`
ON  teachers.id = course_teacher.teacher_id
JOIN `courses`
ON course_teacher.course_id = courses.id
JOIN `degrees`
ON courses.degree_id = degrees.id
JOIN `departments`
ON degrees.department_id = departments.id
WHERE departments.name = 'Dipartimento di Matematica';

