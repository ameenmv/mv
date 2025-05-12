<template>
  <div
    class="
  "
  ></div>
  <!-- <div class="splash">
  <div class="splash_logo">
    BJL
  </div>
  <div class="splash_svg">
    <svg width="100%" height="100%">
      <rect width="100%" height="100%" >
	  </svg>
  </div>
  <div class="splash_minimize">
    <svg width="100%" height="100%">
      <rect width="100%" height="100%" >
	  </svg>
  </div>
</div>
<div class="text">
  <p>Duis quis</p>
  <p>nec sapien</p>
  <button>More</button>
</div> -->
  <!-- <div>

    <div v-if="showSplash" class="splash-screen flash-screen">
      <h1>
        Are You
        <br />
        Ready To
        <br />
        Seeeeeee
        <br />
        My Portfolio ?
        <div class="rockett">
          <img class="rocket" src="../assets/rocket.png" alt="" />
        </div>
      </h1>
      <div class="images position-relative">
        <img class="amendrick" src="../assets/amendrick.jpg" alt="" />
        <div class="spin">
          <img class="cd" src="../assets/cd.png" alt="" />
        </div>
      </div>
    </div>
  </div> -->
</template>

<script>
export default {
  name: "Splash",
  data() {
    return {
      showSplash: true,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showSplash = false;
    }, 2000);
  },
};
</script>

<style scoped>
h1 {
  color: #111217;
  font-weight: 700;
  font-size: 50px;
  letter-spacing: 2px;
  line-height: 1.5;
}
.cd {
  width: 650px;
  animation: spin 2s linear infinite;
  /*  animation: spin 2s linear infinite, moveLeft 2s ease-in-out forwards; */
}
.spin {
  position: absolute;
  z-index: -2;
  right: -300px;
  top: 13%;
  animation: moveLeft 2s ease-in-out forwards;
}
.splash-screen {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #e1e1e1;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  gap: 70px;
}
.main-content {
  padding: 20px;
}
.amendrick {
  margin-right: 150px;
  z-index: -1;
}
.rocket {
  width: 60px;
  transform: rotate(-45deg);
  animation: roket 1.5s ease-in-out forwards;
  z-index: 9999;
}
.rockett {
  animation: rotate 1.5s ease-in-out forwards;
}
.images {
  z-index: -1;
}
@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
@keyframes moveLeft {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-500px);
  }
}
@keyframes roket {
  0% {
    transform: translateX(0);
  }

  100% {
    transform: translate(950px, -320px);
  }
}
@keyframes rotate {
  0% {
    transform: rotate(-45deg);
  }
  100% {
    transform: rotate(10deg);
  }
}
.flash-screen {
  width: 100vw;
  height: 100vh;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  animation: flash 0.3s ease-in-out 1.5s forwards;
  opacity: 1; /* start visible */
}

@keyframes flash {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0; /* back to visible */
    width: 100vw;
    height: 100vh;
  }
}
</style>
