<template>
  <div id="about" ref="section" class="about position-relative">
    <div class="overlay"></div>
    <video
      :class="['floating-box', { fixed: isFixed }]"
      autoplay
      muted
      loop
      src="../assets/me.mp4"
    ></video>
    <div class="text d-flex">
      <div class="one">
        <h1 class="fs-1 mb-4">Who is <span>Ameen Mohamed ?</span></h1>
        <p class="fs-5">
          A Computer Science student at the Faculty of Computers & Information,
          Mansoura University. A dedicated Front-End Developer specialized in
          Vue.js, with additional experience in React. Currently expanding my
          skills in Back-End development using PHP and Laravel through ITI
          training. Passionate about software engineering and clean code, I’m
          eager to build dynamic, responsive, and scalable web applications
          while continuously growing in the tech industry.
        </p>
        <div class="links d-flex">
          <div class="icons">
            <a target="_blank" href="https://github.com/ameenmv">
              <img src="../assets/githubb.png" alt="" />
            </a>
            <a target="_blank" href="https://www.linkedin.com/in/ameeenmv/">
              <img src="../assets/linkedin.png" alt="" />
            </a>

            <a target="_blank" href="https://instagram.com/ameeen_mv">
              <img src="../assets/insta.png" alt="" />
            </a>
          </div>
          <a
            target="_blank"
            href="https://drive.google.com/file/d/1z3-1ywBLo2t6o5o213GaHjmgw6wl73it/view"
          >
            <button>Preview My CV ?</button>
          </a>
        </div>
      </div>
      <div class="two">
        <h1 class="fs-1 mb-4">what can <span>Ameen</span> do ?</h1>
        <p class="fs-5">
          I'm a Front-End Developer with strong experience in Vue.js and solid
          knowledge of React, along with expertise in JavaScript. I focus on
          building efficient, scalable, and user-friendly web applications with
          clean and maintainable code. I’m a fast learner and work closely with
          teams and clients to deliver real-world digital solutions. Let’s
          collaborate to bring your ideas to life.
        </p>
        <div class="links d-flex">
          <div class="icons">
            <a target="_blank" href="https://github.com/ameenmv">
              <img src="../assets/githubb.png" alt="" />
            </a>
            <a target="_blank" href="https://www.linkedin.com/in/ameeenmv/">
              <img src="../assets/linkedin.png" alt="" />
            </a>

            <a target="_blank" href="https://instagram.com/ameeen_mv">
              <img src="../assets/insta.png" alt="" />
            </a>
          </div>
          <a
            target="_blank"
            href="https://drive.google.com/file/d/1z3-1ywBLo2t6o5o213GaHjmgw6wl73it/view"
          >
            <button>Preview My CV ?</button>
          </a>
        </div>
      </div>
      <div class="three">
        <h1>Some of <span>Ameen's</span> skills and Technologies</h1>
        <p class="fs-5 mt-3">
          Vue.js, React.js, JavaScript, TypeScript, Unit Testing, ECMAScript 6,
          HTML, PugJS, Gulp.js, CSS, SASS, Tailwind CSS, Bootstrap, Vuetify, Vue
          Router, Vuex, Pinia, GSAP, Three.js
          <br />
          PHP, Laravel, MySQL, Database, RESTful APIs
          <br />
          Cs50, C++, C#, Python, OOP, DataStructure, Algorithms, Git, GitHub,
          Unit Testing

          <br />
          tap the Preview My CV's button (banner😆) to learn more &nbsp;
          <span class="fs-3">⤦</span>
        </p>
        <div class="links d-flex">
          <div class="icons">
            <a target="_blank" href="https://github.com/ameenmv">
              <img src="../assets/githubb.png" alt="" />
            </a>
            <a target="_blank" href="https://www.linkedin.com/in/ameeenmv/">
              <img src="../assets/linkedin.png" alt="" />
            </a>
            <a target="_blank" href="https://instagram.com/ameeen_mv">
              <img src="../assets/insta.png" alt="" />
            </a>
          </div>
          <a
            target="_blank"
            href="https://drive.google.com/file/d/1z3-1ywBLo2t6o5o213GaHjmgw6wl73it/view"
          >
            <button>Preview My CV ?</button>
          </a>
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
  name: "About",
  setup() {
    const isFixed = ref(false);
    const section = ref(null);

    const onScroll = () => {
      const el = section.value;
      const rect = el.getBoundingClientRect();

      // Section is partially in viewport
      if (rect.top <= 0 && rect.bottom >= 50) {
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
.floating-box.fixed {
  position: fixed;
  top: 0;
  width: 100%;
}
.floating-box {
  position: relative;
  transition: 0.3 ease;
}
.about {
  background: var(--bg-color);
  position: relative;
  height: 370dvh;
}
/*.overlay {
  position: absolute;
  content: "";
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.501);
  z-index: -1;
}*/
video {
  width: 100%;
  height: 100dvh;
  object-fit: cover;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  z-index: 0;
  transition: 0.5s;
}
.text {
  z-index: 3;
  overflow: hidden;
  flex-direction: column;
  position: absolute;
  top: 50%;
  transform: translateY(-40%);
  width: 100%;
  height: 100%;
  height: 320dvh;
  text-align: center;
  align-items: center;
  padding: 75px;
  background: #03031d5d;
}
.one,
.two {
  margin-bottom: 500px;
}
.one,
.two,
.three {
  color: var(--white-color);
}
h1 span {
  color: var(--main-color);
}
.links {
  justify-content: center;
  gap: 150px;
  padding-top: 40px;
}
.links .icons {
  gap: 20px;
  display: flex;
  align-items: center;
}
.links .icons img {
  width: 35px;
  height: 35px;
}
.links button {
  padding: 15px 25px;
  border-radius: 30px;
  font-size: 18px;
  font-weight: 600;
  background: var(--main-color);
  color: var(--white-color);
  transition: var(--transition);
}
.links button:hover {
  background: var(--main-hover);
}
@media (min-width: 1558px) {
  .about {
    height: 280dvh;
  }
  .text {
    height: 270dvh;
  }
}
@media (max-width: 1200px) {
  .about {
    height: 380dvh;
  }
  .text {
    height: 370dvh;
  }
}
@media (max-width: 991px) {
  .text h1 {
    font-size: 32px !important;
  }
  .text p {
    font-size: 18px !important;
  }
  .links .icons img {
    width: 30px;
    height: 30px;
  }
  .links button {
    padding: 12px 20px;
    font-size: 17px;
  }
  .about {
    height: 270dvh;
  }
  .text {
    height: 260dvh;
  }
  .one,
  .two {
    margin-bottom: 300px;
  }
}
@media (max-width: 767px) {
  .text h1 {
    font-size: 28px !important;
  }
  .text {
    padding: 75px 10px;
  }
  .text p {
    font-size: 15px !important;
  }
  .links {
    gap: 50px;
  }
  .links .icons img {
    width: 28px;
    height: 28px;
  }
  .links button {
    padding: 10px 18px;
    font-size: 15px;
  }
}
</style>
