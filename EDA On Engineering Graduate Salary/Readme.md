## EDA On Engineering Graduate Salary Using Python

### Introduction

Exploratory data analysis (EDA) is a vital part of data science as it helps to discover relationships between the entities of the data we are working on. It is helpful to use EDA when we’re dealing with data for the first time. It also helps with large datasets as it is not practically possible to determine relationships with large unknown data. As we deep dive in EDA, we find various patterns which prove to be fruitful for further data processing and modeling.

**Dataset**

For this EDA, we will be using ‘Engineering Graduate Salary’ dataset available on Kaggle. It contains detailed information about the categories available in the data.

**Engineering Graduates in India**

India has a total 6,214 Engineering and Technology Institutions in which around 2.9 million students are enrolled. Every year on an average 1.5 million students get their degree in engineering, but due to lack of skill required to perform technical jobs less than 20 percent get employment in their core domain.

### Objective

A relevant question is what determines the salary and the jobs these engineers are offered right after graduation. Various factors such as college grades, candidate skills, the proximity of the college to industrial hubs, the specialization one have, market conditions for specific industries determine this. On the basis of these various factors, your objective is to determine the salary of an engineering graduate in India.

**Data Description**

* ID: A unique ID to identify a candidate
* Salary: Annual CTC offered to the candidate (in INR)
* Gender: Candidate's gender
* DOB: Date of birth of the candidate
* 10percentage: Overall marks obtained in grade 10 examinations
10board: The school board whose curriculum the candidate followed in grade 10
12graduation: Year of graduation - senior year high school
12percentage: Overall marks obtained in grade 12 examinations
12board: The school board whose curriculum the candidate followed
CollegeID: Unique ID identifying the university/college which the candidate attended for her/his undergraduate
CollegeTier: Each college has been annotated as 1 or 2. The annotations have been computed from the average AMCAT scores obtained by the students in the college/university. Colleges with an average score above a threshold are tagged as 1 and others as 2.
Degree: Degree obtained/pursued by the candidate
Specialization: Specialization pursued by the candidate
CollegeGPA: Aggregate GPA at graduation
CollegeCityID: A unique ID to identify the city in which the college is located in.
CollegeCityTier: The tier of the city in which the college is located in. This is annotated based on the population of the cities.
CollegeState: Name of the state in which the college is located
GraduationYear: Year of graduation (Bachelor's degree)
English: Scores in AMCAT English section
Logical: Score in AMCAT Logical ability section
Quant: Score in AMCAT's Quantitative ability section
Domain: Scores in AMCAT's domain module
ComputerProgramming: Score in AMCAT's Computer programming section
ElectronicsAndSemicon: Score in AMCAT's Electronics & Semiconductor Engineering section
ComputerScience: Score in AMCAT's Computer Science section
MechanicalEngg: Score in AMCAT's Mechanical Engineering section
ElectricalEngg: Score in AMCAT's Electrical Engineering section
TelecomEngg: Score in AMCAT's Telecommunication Engineering section
CivilEngg: Score in AMCAT's Civil Engineering section
conscientiousness: Scores in one of the sections of AMCAT's personality test
agreeableness: Scores in one of the sections of AMCAT's personality test
extraversion: Scores in one of the sections of AMCAT's personality test
nueroticism: Scores in one of the sections of AMCAT's personality test
openess_to_experience: Scores in one of the sections of AMCAT's personality test
