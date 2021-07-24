# My dissertation project: CodeBot

CodeBot is a chatbot application utilized by two main types of users: computer science students and lecturers. CodeBot is hosted online http://www.doc.gold.ac.uk/usr/206/, in the homepage of the
application, the chatbot is available, which responds to student’s queries related to SQL programming language. 

In most cases the chatbot can perform language recognition and respond accordingly. It also has a rating feature and the data collected via
the rating feature is stored into the database and used to create simple statistics. Lecturers can login with CodeBot to view chatbot statistics and edit chatbot’s bank of
SQL related responses.

## Motivation to develop CodeBot
Due to the COVID-19 pandemic, online education has become a current reality for
students. As a result, the education system has changed drastically. Most learning
institutions are now teaching remotely using various digital platforms.
Furthermore, the ratio of students per lecturer is rising, affecting the amount
of personalised learning each student is given. As a consequence of these circumstances,
some students are having poor e-leaning experiences. One of the main issues
is that students are lacking engagement and individualised support. Students
are finding it difficult to ask lecturers questions remotely due to the limited times
online, leading to student dissatisfaction and high dropout rates.
In the best-case scenario, the solution would be to have one lecturer per student.
Obviously, that is not possible due to financial restrictions.

Chatbots have the capability to solve this problem in an effective and cost-efficient
manner. Therefore, with the motivation to enhance the e-learning experience, a platform
independent educational chatbot has been developed, named CodeBot. It is
aimed at computer science university students requiring immediate assistance with
learning the programming language SQL.

CodeBot secondarily aims to take away part of the lecturer’s work load during
the SQL programming sessions, as students can use CodeBot instead, to query about
SQL’s theoretical aspects and syntax issues. CodeBot can upgrade the e-leaning experience
of students as it provides increased interaction in learning at all times and
regardless of the ratio of students per lecturer.

Additionally, many at times, browser searches provide irrelevant information
and require university students to spend a long time searching through various websites. The chatbot provides convenience for students, as it produces fast, quality
based, accurate filtered results. Lecturers will be granted access into the chatbot’s response
bank, so they are able to view and modify the responses up to the satisfactory
standards required to learn about SQL.

## Main technologies used to develop CodeBot:
- NodeJS
- Express.js
- MongoDB database program
- HTML5
- CSS3
- Bcrypt.js
- RESTful API and JSON format
- Google Charts

## CodeBot's accessability for students:
The chatbot  responds to student’s queries related to SQL programming language. 
<img width="848" alt="GUI index" src="https://user-images.githubusercontent.com/60260285/126879640-4cc23298-7b58-4be1-9b33-117ddc442e1e.png">

## CodeBot's accessability for lecturers:
Lecturers can login with CodeBot to view chatbot statistics and edit chatbot’s bank of SQL related responses.
<img width="855" alt="GUI login" src="https://user-images.githubusercontent.com/60260285/126879669-e7da37b4-5b4c-499a-8652-27b30554994e.png">

<img width="473" alt="GUI addtopics" src="https://user-images.githubusercontent.com/60260285/126879676-e6cd3204-fd1c-4c1f-a71d-455ccec436d6.png">

<img width="875" alt="GUI stats" src="https://user-images.githubusercontent.com/60260285/126879679-d742ea09-b7ab-4b18-88c2-03d5ef32d499.png">

## CodeBot's MongoDB database
The database program used for the back-end of the application is MongoDB. The database’s name is “codebotdb”. The database is formed of three collections, which can be seen in the image below.

<img width="290" alt="dbCollections" src="https://user-images.githubusercontent.com/60260285/126880022-dff3d7f8-dec8-4953-a92d-0a916660515a.png">

The records in the “users” collection, is the user registration details which are
used to enable lecturers to log in. Every record in it has a field known as \_id, which
is the unique identifier for that record, in SQL that is known as the primary key.
The next field is the username, then the “password” which is in the “main.js” file
route data validation is applied to, to ensure the minimum length for the password
is 5. Also, the password is never stored in it’s original format, but rather the hashed
password is stored, this is for security reasons. The last field is the “email”, this field
is validated too to ensure the email is valid, this is done in the “main.js” file under
the route “/registered”.

<img width="1401" alt="dbUsers" src="https://user-images.githubusercontent.com/60260285/126880040-a09df185-5315-4d43-b651-41bd4a82f156.png">


The collection “topics” contains records of the chatbot’s responses related to SQL
queries. Apart from the default \_id field, each record has three more fields, the
“name” which stores the keyword or statement name, this field has been validated
in the “main.js” file to ensure the name has a minimum length of three. Another
field is “description” which contains the explanation of the SQL statement. And the
last field is “writtenBy” which contains the name of the individual who wrote this
response.

<img width="1388" alt="dbTopics" src="https://user-images.githubusercontent.com/60260285/126880051-2071f23c-344e-411a-b72d-0efcf0012da9.png">


The collection “ratings” is used to store the rating of a SQL chatbot response.
The field “messageId” is the unique_id of that record from the collection “topics”,
here on the “ratings” collection it has been used to reference the external record, this
would have been the equivalent of a foreign key in SQL. The field “rating” stores the
number of stars the response got.

<img width="1052" alt="dbRatings" src="https://user-images.githubusercontent.com/60260285/126880060-90561ea7-0ac4-40d0-a572-78e30ca0f2b7.png">


All the data in the MongoBD database are in the format BJSON, which is the
binary form of JSON format. This is ideal as BJSON can represent complex structures
like arrays and custom objects.




