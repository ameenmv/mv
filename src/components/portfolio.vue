<template>
  <div id="projects" ref="section" class="portfolio position-relative">
    <div class="container position-relative">
      <div
        :class="['floating-box', { fixed: isFixed }]"
        class="header d-flex justify-content-between"
      >
        <h1 class="heading">My Latest <span>Projects</span></h1>
        <a target="_blank" href="https://github.com/ameenmv"
          ><div class="all d-flex align-items-center gap-3">
            <div class="view">
              <p>View All Projects</p>
            </div>
            <div class="arrow">
              <img src="../assets/arrow.png" alt="" />
            </div></div
        ></a>
      </div>
      <div class="projects d-flex align-items-center">
        <div class="project project1 d-flex gap-5">
          <div class="left">
            <div class="project-name mb-3">KIIIBS</div>
            <div class="bio mb-5">
              KIIIBS is a responsive online store specialized in selling
              keyboards, keycaps, and deskmats. Through building this project, I
              enhanced my design skills, improved my problem-solving and
              research abilities, and deepened my understanding of Vue.js. The
              entire website was designed and styled from scratch without using
              any CSS libraries.
            </div>
            <div class="details d-flex justify-content-between">
              <div class="used d-flex align-items-center">
                #vue #pinia #vulidate
              </div>
              <div class="links">
                <a target="_blank" href="https://kiiibs.netlify.app/"
                  ><img src="../assets/eye.png" alt=""
                /></a>
                <a target="_blank" href="https://github.com/ameenmv/kiiibs"
                  ><img class="me-2 ms-2" src="../assets/github.png" alt=""
                /></a>
              </div>
            </div>
          </div>
          <div class="right">
            <img src="../assets/kibs.png" alt="" />
          </div>
        </div>
        <div class="project project2 d-flex gap-5">
          <div class="left">
            <div class="project-name mb-3">mvclinic</div>
            <div class="bio mb-5">
              Front-End Clinic Appointment System Developed a simple appointment
              booking interface where patients can schedule appointments and
              doctors can accept or reject requests. Built using static JSON
              data for demonstration purposes. Initially intended as a
              full-featured platform, this version represents the completed
              front-end prototype.
            </div>
            <div class="details d-flex justify-content-between">
              <div class="used d-flex align-items-center">
                #Vue.js, #Tailwind CSS, #Pinia
              </div>
              <div class="links">
                <a
                  target="_blank"
                  href="https://www.linkedin.com/posts/ameeenmv_mvclinic-a-simple-clinic-appointment-system-activity-7350590510383669249-FrKP?utm_source=share&utm_medium=member_desktop&rcm=ACoAAE7-DDgB0JrMctQNvAuTEzWA6ty97XuHN8k"
                  ><img src="../assets/eye.png" alt=""
                /></a>
                <a target="_blank" href="https://github.com/ameenmv/mvclinic"
                  ><img class="me-2 ms-2" src="../assets/github.png" alt=""
                /></a>
              </div>
            </div>
          </div>
          <div class="right">
            <img src="../assets/mvclinic.png" alt="" />
          </div>
        </div>
        <div class="project project2 d-flex gap-5">
          <div class="left">
            <div class="project-name mb-3">MV Lib</div>
            <div class="bio mb-5">
              MVLib is an Online Library Management System developed as my final
              project during my ITI internship, a journey full of learning,
              research, and challenges. I designed the entire UI/UX from scratch
              based on my own vision. The system offers an Admin Dashboard to
              manage books, users, and borrowing activities with role-based
              permissions. Students can register, browse books, borrow, and
              manage their profiles and borrowed books.
            </div>
            <div class="details d-flex justify-content-between">
              <div class="used d-flex align-items-center">
                #vue #Tailwind #Axios #Pinia #Vuelidate
              </div>
              <div class="links">
                <a
                  target="_blanc"
                  href="https://www.linkedin.com/posts/ameeenmv_mvlib-online-library-management-system-activity-7361810305875595267-HRIc?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAAE7-DDgB0JrMctQNvAuTEzWA6ty97XuHN8k"
                  ><img src="../assets/eye.png" alt=""
                /></a>
                <a href="https://github.com/ameenmv/MVLibrary" target="_blanc"
                  ><img class="me-2 ms-2" src="../assets/github.png" alt=""
                /></a>
              </div>
            </div>
          </div>
          <div class="right">
            <img class="lopy" src="../assets/mvlib.png" alt="" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import { computed } from "vue";
import { onMounted } from "vue";
import { onBeforeUnmount } from "vue";

export default {
  name: "portfolio",
  setup() {
    const isFixed = ref(false);
    const section = ref(null);

    const onScroll = () => {
      const el = section.value;
      const rect = el.getBoundingClientRect();

      // Section is partially in viewport
      if (rect.top <= 0 && rect.bottom >= 650) {
        isFixed.value = true;
      } else {
        isFixed.value = false;
      }
    };

    const boxStyle = computed(() => {
      if (isFixed.value) {
        return { top: "0px" };
      } else {
        return { top: "auto" };
      }
    });

    onMounted(() => {
      window.addEventListener("scroll", onScroll);
    });

    onBeforeUnmount(() => {
      window.removeEventListener("scroll", onScroll);
    });

    return { section, isFixed, boxStyle };
  },
};
</script>

<style lang="scss" scoped>
.floating-box {
  position: relative;
  transition: 0.3 ease;
}
.header {
  z-index: 100;
  background-color: var(--bg-color);
}
.floating-box.fixed {
  position: fixed;
  padding-top: 35px;
  padding-bottom: 10px;
  padding-left: 10px;
  padding-right: 10px;
  top: 0;
  width: -webkit-fill-available;
  margin-right: 100px;
}
.portfolio {
  background: var(--bg-color);
  padding-top: var(--pt);
  height: 380dvh;
  padding-bottom: var(--spt);
}
.heading {
  color: var(--white-color);
  animation: ani-left linear;
  animation-timeline: view();
  animation-range: entry 0% cover 40%;
}
.heading span {
  color: var(--main-color);
}
.all {
  background-color: var(--main-color);
  height: 58px;
  padding: 2px;
  border-radius: 50px;
  padding-right: 25px;
  cursor: pointer;
  animation: ani-right linear;
  animation-timeline: view();
  animation-range: entry 0% cover 40%;
}
.view {
  padding: 15px;
  background-color: var(--second-color);
  border-radius: 50px;
  color: var(--white-color);
  font-weight: 500;
}
.arrow {
  padding: 4px;
  background-color: var(--white-color);
  border-radius: 50%;
}
.arrow img {
  width: 35px;
  height: 35px;
}
@keyframes ani-left {
  0% {
    opacity: 20%;
    transform: translateX(-100px);
  }
  100% {
    opacity: 100%;
    transform: translateX(0px);
  }
}
@keyframes ani-right {
  0% {
    opacity: 20%;
    transform: translateX(100px);
  }
  100% {
    opacity: 100%;
    transform: translateX(0px);
  }
}

.projects {
  display: flex;
  flex-direction: column-reverse;
  gap: 500px;
  width: 100%;
  position: relative;
  max-height: 350dvh;
  height: 350dvh;
  overflow: hidden;
}
.project1 {
  animation: projectt linear;
  animation-timeline: view();
  animation-range: entry 140% cover;
}
.project2 {
  top: 100%;
}
.links img {
  width: 45px;
  cursor: pointer;
}
.right img {
  width: 700px;
}

.project-name {
  color: var(--white-color);
  font-weight: bold;
  font-size: 35px;
}
.bio,
.used {
  color: var(--white-color);
  font-size: 18px;
}
.details {
  margin-top: 100px;
}

@keyframes projectt {
  0% {
    transform: translateY(0px);
  }
  100% {
    transform: translateY(-700px);
  }
}

@media (min-width: 1550px) {
  .portfolio {
    height: 260dvh;
  }
  .projects {
    height: 240dvh;
    gap: 400px;
  }
  .floating-box.fixed {
    margin-right: 150px;
  }
}

@media (max-width: 1290px) {
  .floating-box.fixed {
    margin-right: 50px;
    align-items: center;
  }
}
@media (max-width: 1200px) {
  .portfolio {
    height: 300dvh;
  }
  .projects {
    height: 280dvh;
    gap: 400px;
  }
  .heading {
    font-size: 32px;
  }
  .all {
    height: 54px;
    padding-right: 14px;
  }
  .view {
    padding: 13px;
    font-size: 15px;
  }
  .arrow {
    width: 40px;
    height: 40px;
  }
  .arrow img {
    width: 30px;
  }
  .right img {
    width: 500px;
  }
  .project-name {
    font-size: 30px;
  }
  .bio {
    font-size: 16px;
  }
  .used {
    font-size: 16px;
  }
  .details {
    margin-top: 0px;
  }
  .details img {
    width: 40px;
  }
  .project {
    align-items: center;
  }
  .lopy {
    height: fit-content;
  }
}
@media (max-width: 991px) {
  .portfolio {
    height: 220dvh;
  }
  .projects {
    height: 200dvh;
    gap: 200px;
  }
  .heading {
    font-size: 30px;
  }
  .all {
    height: 52px;
    padding-right: 12px;
  }
  .view {
    padding: 11px;
    font-size: 14px;
  }
  .arrow {
    width: 35px;
    height: 35px;
  }
  .arrow img {
    width: 30px;
  }
  .right img {
    width: 400px;
  }
  .project-name {
    font-size: 28px;
  }
  .bio {
    font-size: 15px;
  }
  .used {
    font-size: 15px;
  }
  .details {
    margin-top: 0px;
  }
  .details img {
    width: 35px;
  }
  .project {
    align-items: center;
  }
  .lopy {
    height: fit-content;
  }
  .arrow {
    display: flex;
    align-items: center;
  }
  .container-md,
  .container-sm,
  .container {
    max-width: 790px;
  }
}
@media (max-width: 767px) {
  .projects {
    gap: 200px;
  }
  .projects {
    height: 270dvh;
  }
  .portfolio {
    height: 290dvh;
  }
  .project {
    flex-direction: column-reverse;
  }
  .right {
    width: 100%;
    height: 13rem;
  }
  .right img {
    width: 100%;
    height: 100%;
  }
  .floating-box.fixed {
    margin-right: 14px;
    align-items: center;
  }

  .heading {
    font-size: 26px;
  }
  .all {
    height: 46px;
    padding-right: 10px;
  }
  .view {
    padding: 11px;
    font-size: 13px;
  }
  .arrow {
    width: 32px;
    height: 32px;
  }
  .arrow img {
    width: 25px;
    height: 25px;
  }
}
/*@media (max-width: 550px) {
  .portfolio {
    height: 250dvh;
  }
  .projects {
    height: 230dvh;
    gap: 200px;
  }
}
*/
@media (max-width: 500px) {
  .floating-box.fixed {
    margin-right: 8px;
  }
  .heading {
    font-size: 20px;
  }
  .all {
    height: 38px;
    padding-right: 9px;
  }
  .view {
    padding: 7px;
    font-size: 11px;
  }
  .arrow {
    width: 30px;
    height: 30px;
  }
  .arrow img {
    width: 23px;
    height: 23px;
  }
}
@media (max-width: 400px) {
  .heading {
    font-size: 18px;
  }
  .view {
    font-size: 10px;
  }
}
</style>
