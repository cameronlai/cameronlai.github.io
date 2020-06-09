---
title:  "Exam Timetable Generator"
last_modified_at: 2015-03-07T18:01:00+08:00
header:
  overlay_image: /assets/images/exam-timetable-generator-screenshot.jpg
  teaser: /assets/images/exam-timetable-generator-screenshot.jpg
categories:
  - Project
tags:
  - Web App
---
Optimise exam timetable by maximising revision time between subjects

Did you remember the times when you had exams in a row? 

Did you ever wonder how did the school arrange these awful exam timetables? 

I had a number of these experiences and wanted to find ways to improve the situation. That’s why I started this project, trying to optimize exam timetables automatically. 

## Idea Overview

The idea of a highly optimised exam timetable will be very useful to teachers in arranging timetables. Although some timetable software are able to handle this task, it is still very troublesome to juggle the schedule of all students.

The backend API algorithm uses genetic algorithm to maximize the minimum revision time between subjects for students. This ensures students will all have some time to study before the next exam subject comes. The current version assumes each exam is one-hour only and the subject duration will be able to be varied in the future.

## Migration from Django to Static Website + REST API

The first implementation source code in 2015 with a Django framework can be found [here](https://github.com/cameronlai/EXT_GEN). Django was picked to allow frontend and backend to use the same repository and the same programming language.

The new approach done in 2020 June uses Vue JS as frontend and it is hosted Github Static Website. The backend is still written in Python and is hosted Google Cloud Functions.

The main motivation to do the migration is for the following reason

- Reduce server cost from hosting the Django application
    - Originally, I hosted on Digital Ocean  and it costs $5 a month
- Adopt a more modernize web approach with separate frontend and backend
    - This also decouples the display and exam timetable optimisation logic

Also, revisiting the project again after 5 years allowed me to include a few more touches to make it more user friendly.

- Allow edit of data within the website, instead of using CSV files
- Allow visualisation of timeslots directly with the new "Visualise Time Slots" button

Hope you enjoyed both the exam timetable generator web app and the migration write up! 😃

{% include figure image_path="/assets/images/exam-timetable-generator-screenshot.jpg"  alt="Exam Timetable Generator Screenshot" caption="Exam Timetable Generator Screenshot" %}
