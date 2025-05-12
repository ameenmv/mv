<template>
  <div class="home">
    <div class="background gap-5">
      <div class="overlay">
        <Navbar />
        <landingpage />
      </div>
      <About />
      <portfolio />
      <Contact />
      <Footer />
    </div>
  </div>
</template>

<script>
import Splash from "@/components/splash.vue";
import Navbar from "../components/Navbar.vue";
import Landingpage from "@/components/Landingpage.vue";
import Portfolio from "@/components/portfolio.vue";
import About from "@/components/About.vue";
import Contact from "@/components/contact.vue";
import Footer from "@/components/footer.vue";
export default {
  name: "Home",
  components: {
    Navbar,
    Splash,
    Landingpage,
    Portfolio,
    About,
    Contact,
    Footer,
  },
};
</script>

<style lang="scss" scoped>
.home {
  height: 100vh;
}
.background {
  background-image: url(../assets/backgroundd.jpg);
  background-size: cover;
  width: 100%;
  height: 100vh;
  z-index: -2;
}
.overlay {
  width: 100%;
  height: 100vh;
  z-index: -1;
  background: #00000056;
}
@media (max-width: 767px) {
  .home,
  .background,
  .overlay {
    height: 100vh;
  }
}
</style>
