<template>
  <div class="footer">
    <div class="container">
      <p>Ameen Mohamed © All Rights Reserved - 2025</p>
      <div class="links">
        <a target="_blank" href="https://instagram.com/ameeen_mv"
          ><img src="../assets/insta.png" alt=""
        /></a>
        <a target="_blank" href="https://x.com/ameeen_mv"
          ><img src="../assets/twitter.png" alt=""
        /></a>
        <a target="_blank" href="https://wa.me/201017025076"
          ><img src="../assets/whats.png" alt=""
        /></a>
        <a target="_blank" href="https://github.com/ameenmv"
          ><img src="../assets/githubb.png" alt=""
        /></a>
        <a target="_blank" href="https://linkedin.com/in/ameeenmv"
          ><img src="../assets/linkedin.png" alt=""
        /></a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style lang="scss" scoped>
.footer {
  background: var(--bg-color);
  padding-top: 30px;
  padding-bottom: 20px;
  color: var(--white-color);
  border-top: 1px solid #915eff62;
}
.container {
  display: flex;
  justify-content: center;
  gap: 100px;
}
.links {
  display: flex;
  gap: 20px;
  flex-basis: 50%;
}
p {
  flex-basis: 50%;
  text-align: end;
}
.links img {
  width: 25px;
  cursor: pointer;
}
@media (max-width: 991px) {
  .container-md,
  .container-sm,
  .container {
    max-width: 875px;
  }
  .links {
    justify-content: end;
    flex-basis: 24%;
  }
  p {
    font-size: 15px;
    display: flex;
  }
  .links img {
    width: 22px;
  }
}
@media (max-width: 767px) {
  .container {
    flex-direction: column-reverse;
  }
  .links {
    justify-content: left;
  }
  .container {
    gap: 30px;
  }
  p {
    font-size: 14px;
  }
}
</style>
