<template>
  <div>
    <Work>
      <template #year> 2021 </template>
      <template #title> Marugo Class Web App & LINE Chatbot </template>
      <template #coverImg>
        <img src="/images/marugo-mock-up.jpg" alt="marugo class" />
      </template>
      <template #url> Working in progress</template>
      <template #role>
        <ul>
          <li>Front-end development</li>
          <li>
            Planning SQL database on ER digram and writing API doc for back-end
            developer
          </li>
          <li>UI/UX design</li>
        </ul>
      </template>
      <template #technologies> Vue.js, Express.js, Adobe XD </template>
      <template #description>
        <!-- Description -->
        <section class="mb-20">
          <h2 class="fw-bold font-l mb-8">
            Marugo Class Web App & LINE Chatbot
          </h2>
          <p>
            Marugo Class Web Application and its LINE Chatbot aim for improving
            teaching and learning experiences of tutorial classes in Taiwan.
            While web application has a complete set of features for students
            and teachers to manage their materials on web, LINE Chatbots is
            built for students to quickly access the core features they needed
            for their studies with only a few clicks on their phones.
          </p>
        </section>
        <!-- LINE Chatbot -->
        <section class="mb-20">
          <h2 class="fw-bold font-l mb-8">Marugo Class LINE Chatbot</h2>
          <p class="mb-8">
            Marugo Class LINE Chatbot focuses on few core features that helps
            students to manage their learning materials:
          </p>
          <ul>
            <li>Check course schedules or date and time of the next lesson</li>
            <li>Submit or review assignments records</li>
            <li>Create notes</li>
            <li>Send reminder of the next lessons to students</li>
          </ul>
        </section>
      </template>
      <template #content>
        <!-- <div class="mb-20">
          <h2 class="font-m mb-8">Rich Menu</h2>
          <img src="/images/richmenu.jpg" alt="rich menu" />
        </div> -->
        <section class="mb-20">
          <h2 class="font-m mb-8">LINE Chatbot features</h2>
          <img src="/images/show_next_lesson_and_reminder.jpg" alt="" />
        </section>
        <section class="mb-21">
          <h2 class="font-m mb-8">Connect with Web App through LIFF browser</h2>
          <img src="/images/show_liff.jpg" alt="lliff" />
        </section>
        <section>
          <div class="row justify-content-center">
            <div>
              <h2 class="fw-bold font-l mb-8">Marugo Class Web App</h2>
              <p class="mb-18">
                Compared to chatbot, Marugo Class Web App provides more advance
                features for students and teachers to manage their learning
                materials.
              </p>
              <!-- Feature for students -->
              <div class="mb-14">
                <p class="mb-2 fw-bold">Features for students:</p>
                <ul>
                  <li>Register course</li>
                  <li>Check lesson schedule</li>
                  <li>Review handouts</li>
                  <li>Submit assignments and review assignment records</li>
                  <li>Create and review notes</li>
                </ul>
              </div>
              <!-- Feature for teachers -->
              <div class="mb-14">
                <p class="mb-2 fw-bold">Features for teachers:</p>
                <ul>
                  <li>Create courses and lessons</li>
                  <li>Create handouts with hashtags</li>
                  <li>Create and review assignments submitted by students</li>
                  <li>Check lesson schedule</li>
                </ul>
              </div>
              <!-- Common features -->
              <div class="mb-21">
                <p class="mb-2 fw-bold">
                  Common features for both teachers and students:
                </p>
                <ul>
                  <li>Log in and log out with token-based authentication</li>
                  <li>Edit personal account information</li>
                </ul>
              </div>
              <!-- Images: Common Features -->
              <section class="mb-21">
                <h2 class="mb-18 fw-bold font-l">Common Features</h2>
                <div class="row">
                  <div class="col-lg-6 mb-18 mb-lg-0">
                    <!-- Review all materials -->
                    <div>
                      <p class="text-info font-s mb-3">Review all material</p>
                      <img
                        class="mb-4"
                        src="images/teacher-my-coourses.jpg"
                        alt=""
                      />
                    </div>
                  </div>
                  <div class="col-lg-6 mb-18 mb-lg-0">
                    <!-- Schedule -->
                    <div>
                      <p class="text-info font-s mb-3">
                        Schedule of all lessons
                      </p>
                      <img src="images/teacher_schedule.jpg" alt="" />
                    </div>
                  </div>
                </div>

                <!-- Responsive -->
                <!-- <div class="row">
                  <p class="text-info font-s mb-3">Responsive</p>
                  <div class="col-6">
                    <img src="images/login_mobile.png" alt="" />
                  </div>
                  <div class="col-6">
                    <img src="images/teacher_my_course_mobile.jpg" alt="" />
                  </div>
                </div> -->
              </section>
              <!-- Images: Features for teachers -->
              <section class="mb-21">
                <h2 class="mb-18 fw-bold font-l">Features for teachers</h2>
                <div class="row mb-lg-18">
                  <!-- CRUD course -->
                  <div class="col-lg-6 mb-18 mb-lg-0">
                    <p class="text-info font-s mb-3">
                      Create, edit or delete lesson
                    </p>
                    <img src="images/teacher_edit_lesson.jpg" alt="" />
                  </div>
                  <!-- CRUD lesson -->
                  <div class="col-lg-6 mb-18 mb-lg-0">
                    <p class="text-info font-s mb-3">
                      Create, edit or delete course
                    </p>
                    <img src="images/teacher_create_course.jpg" alt="" />
                  </div>
                </div>
                <div class="row">
                  <!-- Grade assignment -->
                  <div class="col-lg-6 mb-18 mb-lg-0">
                    <p class="text-info font-s mb-3">
                      Review student's assignment
                    </p>
                    <img src="images/teacher_grade_assignment.jpg" alt="" />
                  </div>
                  <!-- Review all lessons -->
                  <div class="col-lg-6 mb-18 mb-lg-0">
                    <p class="text-info font-s mb-3">Review all lessons</p>
                    <img src="images/teacher_all_lessons.jpg" alt="" />
                  </div>
                </div>
              </section>
              <!-- Images: Features for students -->
              <section class="mb-21">
                <h2 class="mb-18 fw-bold font-l">Features for students</h2>
                <div class="row mb-20">
                  <!-- Submit assignment -->
                  <div class="col-lg-6 mb-18 mb-lg-0">
                    <p class="text-info font-s mb-3">Submit assignment</p>
                    <img src="images/student_submit_assignment.jpg" alt="" />
                  </div>
                  <!-- Review lesson's handout -->
                  <div class="col-lg-6 mb-18 mb-lg-0">
                    <p class="text-info font-s mb-3">Review lesson's handout</p>
                    <img src="images/student_review_handout.jpg" alt="" />
                  </div>
                </div>
                <div class="row">
                  <!-- Grade assignment -->
                  <div class="col-lg-6 mb-18 mb-lg-0">
                    <p class="text-info font-s mb-3">
                      Enable or disable reminder
                    </p>
                    <img src="images/student_reminder.jpg" alt="" />
                  </div>
                  <!-- Review all lessons -->
                  <div class="col-lg-6 mb-18 mb-lg-0">
                    <p class="text-info font-s mb-3">Register course</p>
                    <img src="images/student_register_course.jpg" alt="" />
                    <img src="" alt="" />
                  </div>
                </div>
              </section>
              <!-- Images: Responsive -->
              <section class="mb-21">
                <h2 class="mb-18 fw-bold font-l">Responsive design</h2>
                <div class="row">
                  <div class="col-3">
                    <!-- <p class="text-info font-s mb-3">Submit assignment</p> -->
                    <img src="images/login_mobile.png" alt="" />
                  </div>
                  <div class="col-3">
                    <!-- <p class="text-info font-s mb-3">Review lesson's handout</p> -->
                    <img
                      src="images/student_register_course_mobile.png"
                      alt=""
                    />
                  </div>
                  <div class="col-3">
                    <!-- <p class="text-info font-s mb-3">Review lesson's handout</p> -->
                    <img src="images/student_handout_mobile.png" alt="" />
                  </div>
                  <div class="col-3">
                    <!-- <p class="text-info font-s mb-3">Review lesson's handout</p> -->
                    <img
                      src="images/student_review_handout_lightbox_mobile.png"
                      alt=""
                    />
                  </div>
                </div>
              </section>
              <section>
                <h2 class="mb-18 fw-bold font-l">
                  Remote collaboration with back-end developer
                </h2>
                <h3 class="font-m mb-6">My role</h3>
                <ul class="mb-18">
                  <li>ER diagram design for SQL database</li>
                  <li>Planning chatbot development with flowchart</li>
                  <li>Writing API documentation on Apiary</li>
                  <li>
                    Communication with a back-end developer through Discord and
                    manage all materials together on Notion
                  </li>
                </ul>
                <p class="text-info font-s mb-3">ER digram for Web App</p>
                <img
                  class="mb-20"
                  src="images/LIFF-APP---ER-diagram---0616.jpg"
                  alt=""
                />
                <p class="text-info font-s mb-3">
                  Flowchart of how to send reminder to student by pushing
                  message on LINE chatbot
                </p>
                <img src="images/liff_flowchart.jpg" alt="liff_flowchart" />
              </section>
            </div>
          </div>
        </section>
      </template>
    </Work>
  </div>
</template>

<script>
import Work from '@/components/Work'

export default {
  components: {
    Work,
  },
}
</script>

<style lang="scss" scoped>
li {
  list-style-type: disc;
  list-style-position: inside;
}

.full-img {
  height: 640px;
  width: 100%;
}
</style>
