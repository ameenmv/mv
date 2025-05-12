<template>
  <div ref="landing" class="landing">
    <div class="container d-flex">
      <div class="left">
        <div class="position-relative grap">
          <div class="square square1"></div>
          <div class="square square2"></div>
          <div class="square square3"></div>
          <div class="square square4"></div>
          <p class="mb-4 hello">Hello There !</p>
        </div>
        <div class="d-flex align-items-center">
          <h1 class="im">I'm <span>Ameeen</span></h1>
          <div class="bird mb-3 ms-3">
            <img src="../assets/bird.gif" alt="" />
          </div>
        </div>

        <h1 class="im">Front-end Developer</h1>
        <div class="work mt-5 ms-3 d-flex align-items-center">
          <div class="circle"></div>
          <p class="ms-3">Available To Work</p>
        </div>
        <div class="links d-flex">
          <div class="icons">
            <a target="_blank" href="https://github.com/ameenmv">
              <img src="../assets/githubb.png" alt="" />
            </a>
            <a target="_blank" href="https://linkedin.com/in/ameeenmv">
              <img src="../assets/linkedin.png" alt="" />
            </a>
            <a target="_blank" href="https://instagram.com/ameeen_mv">
              <img src="../assets/insta.png" alt="" />
            </a>
          </div>
        </div>
      </div>
      <div class="right">
        <img class="man" src="../assets/man.svg" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Landingpage",
  methods: {},
};
</script>

<style lang="scss" scoped>
.bird img {
  width: 120px;
  animation: fromright 1s linear;
}
.landing {
  height: 84dvh;
  color: var(--white-color);
}
.container {
  position: relative;
  padding-top: 80px;
  justify-content: space-between;
}
.grap {
  position: relative;
  width: fit-content;
  animation: apperleft 0.5s linear;
}
.square {
  position: absolute;
  content: "";
  width: 15px;
  height: 10px;
  border: 1px solid var(--white-color);
  background: var(--main-color);
}
.square1 {
  left: -7px;
  top: -5px;
}
.square2 {
  left: -7px;
  bottom: -5px;
}
.square3 {
  right: -7px;
  top: -5px;
}
.square4 {
  right: -7px;
  bottom: -5px;
}
.im {
  font-size: 57px;
  font-weight: bold;
  color: var(--white-color);
  animation: apperbottom 0.5s linear;
  animation-delay: 0.5s;
  animation-fill-mode: backwards;
}
.im span {
  color: var(--main-color);
}
.hello {
  color: var(--white-color);
  font-size: 25px;
  border: 1px solid var(--white-color);
  width: fit-content;
  padding: 8px;
}
.work {
  animation: up-down 2s infinite;
}
.circle {
  width: 10px;
  height: 10px;
  background: var(--white-color);
  border-radius: 50%;
}
.links {
  margin-top: 10px;
}
.links .icons {
  gap: 40px;
  display: flex;
  align-items: center;
  margin-left: 15px;
  margin-top: 70px;
}
.links .icons img {
  width: 35px;
  height: 35px;
}
.landing .right .man {
  width: 500px;
  animation: up-down 4s infinite;
}

@keyframes up-down {
  0%,
  100% {
    transform: translateY(40px);
  }
  50% {
    transform: translateY(-30px);
  }
}
@keyframes apperbottom {
  0% {
    opacity: 0%;
    transform: translateY(80px);
  }
  100% {
    opacity: 100%;
    transform: translateY(0);
  }
}
@keyframes apperleft {
  0% {
    opacity: 0%;
    transform: translateX(-80px);
  }
  50% {
    opacity: 20%;
  }
  100% {
    opacity: 100%;
    transform: translateX(0);
  }
}
@keyframes fromright {
  0% {
    transform: translateX(200px);
  }
  100% {
    transform: translateX(0px);
  }
}

@media (max-width: 1200px) {
  .hello {
    font-size: 22px;
  }
  .im {
    font-size: 50px;
  }
  .work {
    font-size: 15px;
  }
  .icons img {
    width: 30px !important;
    height: 30px !important;
  }
  .landing .right .man {
    width: 400px;
  }
}
@media (max-width: 991px) {
  .hello {
    font-size: 20px;
  }
  .im {
    font-size: 37px;
  }
  .work {
    font-size: 14px;
  }
  .icons img {
    width: 25px !important;
    height: 25px !important;
  }
  .landing .right .man {
    width: 300px;
  }
}
@media (max-width: 767px) {
  .landing {
    height: 70dvh;
  }
  .hello {
    font-size: 18px;
  }
  .im {
    font-size: 33px;
  }
  .work {
    font-size: 13px;
  }
  .icons img {
    width: 22px !important;
    height: 22px !important;
  }
  .landing .right .man {
    display: none;
  }
}
</style>
