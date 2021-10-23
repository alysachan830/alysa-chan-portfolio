---
title: Marugo Class Web App & LINE Chatbot
year: 2021
coverImg: /images/marugo-mock-up.jpg
url: Working in progress
role: Front-end development, Planning SQL database on ER digram and writing API doc for back-end developer, UI/UX design
technologies: Vue.js, Express.js, Adobe XD
description: Marugo Class Web Application and its LINE Chatbot aim for improving
  teaching and learning experiences of tutorial classes in Taiwan.
  While web application has a complete set of features for students
  and teachers to manage their materials on web, LINE Chatbots is
  built for students to quickly access the core features they needed
  for their studies with only a few clicks on their phones.
---

## Marugo Class LINE Chatbot

<section class="mb-20">

Marugo Class LINE Chatbot focuses on few core features that helps students to manage their learning materials:

- Check course schedules or date and time of the next lesson
- Submit or review assignments records
- Create notes
- Send reminder of the next lessons to students

</section>

<section class="mb-20">
    <span class="caption">LINE chatbot features</span>
    <img src="/images/show_next_lesson_and_reminder.jpg">
</section>

<section class="mb-21">
    <div class="caption">Connect with Web App through LIFF browser</div>
    <img src="/images/show_liff.jpg">
</section>

<section class="mb-20">

## Marugo Class Web App

<p class="mb-18">
Compared to chatbot, Marugo Class Web App provides more advance features for students and teachers to manage their learning materials.
</p>

**Features for students:**

- Register course
- Check lesson schedule
- Review handouts
- Submit assignments and review assignment records
- Create and review notes

**Features for teachers:**

- Create courses and lessons
- Create handouts with hashtags
- Create and review assignments submitted by students
- Check lesson schedule

**Common features for both teachers and students:**

- Create courses and lessons
- Create handouts with hashtags
- Create and review assignments submitted by students
- Check lesson schedule

</section>

<section class="mb-21">

## Common Features

<image-wrap :images="[{url: '/images/teacher-my-coourses.jpg', caption: 'Review all material'}, 
{url: '/images/teacher_schedule.jpg', caption: 'Schedule of all lessons'}]">
</image-wrap>

</section>

<section class="mb-21">

## Features for teachers

<image-wrap :images="[{url: '/images/teacher_edit_lesson.jpg', caption: 'Create, edit or delete lesson'}, 
{url: '/images/teacher_create_course.jpg', caption: 'Create, edit or delete course'}]">
</image-wrap>

<image-wrap :images="[{url: '/images/teacher_grade_assignment.jpg', caption: `Review student's assignment`}, 
{url: '/images/teacher_all_lessons.jpg', caption: 'Review all lessons'}]">
</image-wrap>

</section>

<section class="mb-21">

## Features for students

<image-wrap :images="[
{url: '/images/student_submit_assignment.jpg', caption: 'Submit assignment'}, 
{url: '/images/student_review_handout.jpg', caption: `Review lesson's handout`}
]">
</image-wrap>

<image-wrap :images="[
{url: '/images/teacher_grade_assignment.jpg', caption: 'Enable or disable reminder'}, 
{url: '/images/student_register_course.jpg', caption: 'Register course'}
]">
</image-wrap>

</section>

<section class="mb-21">

## Responsive design

<image-wrap :images="[
{url: '/images/login_mobile.png'},
{url: '/images/student_register_course_mobile.png'},
{url: '/images/student_handout_mobile.png'},
{url: '/images/student_review_handout_lightbox_mobile.png'},
]" :is-responsive="false"> </image-wrap>

</section>

<section class="mb-20">

## Remote collaboration with back-end developer

My role

- Design ER diagram for SQL database
- Plan chatbot development with flowchart
- Write API documentation on Apiary
- Communicate with a back-end developer through Discord and manage all materials together on Notion

</section>

<section class="mb-20">
    <span class="caption">LINE chatbot features</span>
    <img src="/images/LIFF-APP---ER-diagram---0616.jpg">
</section>

<section class="mb-20">
    <span class="caption">Flowchart of how to send reminder to student by pushing message on LINE chatbot</span>
    <img src="/images/liff_flowchart.jpg">
</section>

<!-- <image-wrap class="pt-8">
    <template #img>
        <img src="images/show_next_lesson_and_reminder.jpg">
    </template>
</image-wrap> -->
