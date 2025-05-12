<template>
  <div id="contact" class="contact">
    <div class="container">
      <div class="header">
        <img class="call" src="../assets/callme.png" alt="" />
        <h1 class="mt-4">"Every great dream begins with a dreamer"</h1>
        <p class="mt-3">got a project ? just call me</p>
      </div>
      <div class="text d-flex">
        <div class="left">
          <h2 class="mb-5">GET IN TOUCH</h2>
          <div class="mail d-flex mb-5 align-items-center">
            <img src="../assets/mail.png" alt="" />
            <p class="ms-3">ameeenmv@gmail.com</p>
          </div>
          <div class="address d-flex mb-5 align-items-center">
            <img src="../assets/location.png" alt="" />
            <p class="ms-3">Egypt , Mansoura</p>
          </div>
          <div class="phone d-flex align-items-center">
            <img src="../assets/phone.png" alt="" />
            <p class="ms-3">+201017025076</p>
          </div>
        </div>
        <form @submit.prevent="handleSubmit">
          <div class="right d-flex">
            <input
              required
              v-model="form.name"
              class="name"
              type="name"
              name="name"
              placeholder="Name"
            />
            <input
              required
              v-model="form.email"
              class="mail"
              type="email"
              name="email"
              placeholder="Email"
            />
            <textarea
              required
              v-model="form.message"
              class="message"
              placeholder="Message"
              name="message"
              id=""
            ></textarea>
            <input type="hidden" name="_next" value="/#contact" />
            <button type="submit">Send</button>
            <p v-if="success">
              ✅ Thank you! Your message has been sent successfully.
            </p>
            <p v-if="error">
              ❌ Oops! Something went wrong. Plaease try again.
            </p>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Contact",
  data() {
    return {
      form: {
        name: "",
        email: "",
        message: "",
      },
      success: false,
      error: false,
    };
  },
  methods: {
    async handleSubmit() {
      const formData = new FormData();
      formData.append("name", this.form.name);
      formData.append("email", this.form.email);
      formData.append("message", this.form.message);
      formData.append("_captcha", "false"); // optional
      formData.append("_subject", "New Contact Form Submission");

      try {
        const response = await fetch(
          "https://formsubmit.co/ameeenmv@gmail.com",
          {
            method: "POST",
            body: formData,
          }
        );

        if (response.ok) {
          this.success = true;
          this.error = false;
          this.form.name = "";
          this.form.email = "";
          this.form.message = "";
          setTimeout(() => {
            this.success = false;
          }, 4000);
        } else {
          throw new Error("Failed");
        }
      } catch (err) {
        this.success = false;
        this.error = true;
      }
      setTimeout(() => {
        this.error = false;
      }, 4000);
    },
  },
};
</script>

<style lang="scss" scoped>
.contact {
  background: var(--bg-color);
  padding-top: var(--pt);
  color: var(--white-color);
  padding-bottom: 100px;
}
.contact .header {
  text-align: center;
}
.contact .header h1 {
  color: var(--main-color);
  font-weight: bold;
  font-size: 38px;
}
.contact .header p {
  color: var(--white-color);
  font-weight: bold;
  font-size: 22px;
}
.contact .call {
  width: 200px;
}
.contact .text {
  margin-top: 80px;
  justify-content: space-between;
}
.contact .text .left img {
  width: 35px;
}
.contact .text .left p {
  color: var(--white-color);
}
.contact .text .right {
  flex-direction: column;
  gap: 30px;
}
.contact .text .right .name,
.contact .text .right .mail,
.contact .text .right textarea {
  width: 900px;
  padding: 15px;
  border-radius: 10px;
  background: transparent;
  outline: none;
  color: var(--white-color);
  border: 1px solid var(--main-color);
}
.contact .text .right textarea {
  height: 200px;
}
.contact .text .right button {
  background: var(--main-color);
  width: 900px;
  padding: 5px;
  border-radius: 10px;
  color: var(--white-color);
}
@media (max-width: 1290px) {
  .contact .text .right .name,
  .contact .text .right .mail,
  .contact .text .right textarea,
  .contact .text .right button {
    width: 800px;
  }
}
@media (max-width: 1200px) {
  .contact .text .right .name,
  .contact .text .right .mail,
  .contact .text .right textarea,
  .contact .text .right button {
    width: 600px;
  }
}
@media (max-width: 991px) {
  .contact .text .right .name,
  .contact .text .right .mail,
  .contact .text .right textarea,
  .contact .text .right button {
    width: 400px;
  }
  .call {
    width: 180px !important;
  }
  .header h1 {
    font-size: 31px !important;
  }
  .header p {
    font-size: 20px !important;
  }
  .left h2 {
    font-size: 26px;
  }
  .contact .text .left img {
    width: 28px;
  }
  .contact .text .left p {
    font-size: 15px;
  }
}
@media (max-width: 767px) {
  .contact .text {
    flex-direction: column;
  }
  .contact .text .right .name,
  .contact .text .right .mail,
  .contact .text .right textarea,
  .contact .text .right button {
    width: 100%;
  }
  .call {
    width: 160px !important;
  }
  .header h1 {
    font-size: 29px !important;
  }
  .header p {
    font-size: 17px !important;
  }
  .left h2 {
    font-size: 24px;
  }
  .contact .text .left img {
    width: 26px;
  }
  .contact .text .left p {
    font-size: 14px;
  }
  .left h2,
  .mail,
  .address {
    margin-bottom: 2rem !important;
  }
  .phone {
    margin-bottom: 3rem;
  }
  input.mail {
    margin-bottom: 0px !important;
  }
}
</style>
