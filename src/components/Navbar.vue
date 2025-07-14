<template>
  <div class="navbar">
    <div class="container d-flex justify-space-between p-2">
      <div class="d-flex align-center">
        <a href="#">
          <img class="ameen" src="../assets/mv.png" alt="" />
        </a>
        <!-- <div
          class="text-white d-flex align-items-center ms-2 mt-2 fs-5 fw-bold"
        >
          Ameen
        </div> -->
      </div>
      <div class="links d-flex align-items-center gap-5">
        <ul ref="target" class="gap-5 fs-5">
          <a class="one" href="#about"><li>About</li></a>
          <a class="two" href="#projects"><li>Projects</li></a>
          <a class="three" href="#contact"><li>Contact</li></a>
        </ul>
        <a
          href="https://drive.google.com/uc?export=download&id=1IlY_RkG4bRIPlrPmX-l8QCX9rJsiE6hn"
        >
          <button class="btn rounded-pill fw-semibold">My CV ?</button>
        </a>
        <div @click="addClassToTarget" class="bars">
          <div ref="one" class="line"></div>
          <div ref="two" class="line"></div>
          <div ref="three" class="line"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "Navbar",
  methods: {
    addClassToTarget() {
      const el = this.$refs.target;
      el.classList.toggle("active");

      // const one = this.$refs.one;
      const two = this.$refs.two;
      // const three = this.$refs.three;
      // one.classList.toggle("onetoggle");
      two.classList.toggle("twotoggle");
      // three.classList.toggle("threetoggle");
    },
  },
};
</script>

<style lang="scss" scoped>
.ameen {
  width: 60px;
  cursor: pointer;
}
.bars {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: var(--main-color);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 4px;
  display: none;
  transition: var(--transition);
}
.bars:hover {
  background: var(--main-hover);
}
.bars .line {
  height: 2px;
  width: 18px;
  background: var(--white-color);
  border-radius: 10px;
  transition: var(--transition);
}
.navbar {
  background: transparent;
  height: 14dvh;
}
.btn {
  background: var(--main-color);
  color: var(--white-color);
  padding: 8px 35px;
  transition: var(--transition);
}
.btn:hover {
  background: var(--main-hover);
}
.links {
  position: relative;
}
.links ul {
  display: flex;
}
ul li {
  cursor: pointer;
  color: var(--white-color);
  transition: var(--transition);
}
ul li:hover {
  color: var(--main-color);
  font-size: 1.25rem;
}
@media (max-width: 1199px) {
  .links ul li {
    font-size: 18px !important;
  }
  .btn {
    padding: 6px 30px;
  }
  .ameen {
    width: 55px;
  }
}
@media (max-width: 991px) {
  .links ul li {
    font-size: 17px !important;
  }
  .btn {
    padding: 5px 28px;
  }
  .ameen {
    width: 50px;
  }
}
@media (max-width: 767px) {
  .links ul {
    display: none;
  }
  .active {
    display: flex !important;
    position: absolute;
    top: 60px;
    right: -5px;
    z-index: 5;
    background: var(--main-color);
    flex-direction: column;
    gap: 0px !important;
    align-items: end;
    border-radius: 8px;
  }
  .active::before {
    content: "";
    border-width: 12px;
    border-style: solid;
    border-color: transparent transparent var(--main-color) transparent;
    position: absolute;
    right: 12px;
    top: -23px;
  }
  .active a {
    padding: 15px 30px;
    display: flex;
    align-items: center;
    text-align: center;
    justify-content: center;
    width: 100%;
    transition: var(--transition);
  }
  .one {
    border-top-left-radius: 8px;
    border-top-right-radius: 8px;
  }
  .three {
    border-bottom-left-radius: 8px;
    border-bottom-right-radius: 8px;
  }
  .active a:hover {
    background: var(--main-hover);
  }
  .active li:hover {
    color: var(--white-color);
  }
  .bars {
    display: flex;
  }
  .twotoggle {
    transform: translateX(5px);
  }

  .links {
    gap: 1rem !important;
  }
}
</style>
