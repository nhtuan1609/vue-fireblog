<template>
  <div class="form-wrap">
    <form action="" class="register">
      <p class="login-register">
        Aldready have an account?
        <router-link class="router-link" :to="{ name: 'Login' }">
          Login
        </router-link>
      </p>
      <h2>Create Your FireBlog Account</h2>
      <div class="inputs">
        <div class="input">
          <input type="text" placeholder="First Name" v-model="firstName" />
          <User class="icon" />
        </div>
        <div class="input">
          <input type="text" placeholder="Last Name" v-model="lastName" />
          <User class="icon" />
        </div>
        <div class="input">
          <input type="text" placeholder="Username" v-model="userName" />
          <User class="icon" />
        </div>
        <div class="input">
          <input type="text" placeholder="Email" v-model="email" />
          <Email class="icon" />
        </div>
        <div class="input">
          <input type="password" placeholder="Password" v-model="password" />
          <Password class="icon" />
        </div>
      </div>
      <button>Sign Up</button>
      <div class="angle"></div>
    </form>
    <div class="background"></div>
  </div>
</template>

<script>
import Email from "@/assets/Icons/envelope-regular.svg";
import Password from "@/assets/Icons/lock-alt-solid.svg";
import User from "@/assets/Icons/user-alt-light.svg";

export default {
  name: "Register",
  components: { Email, Password, User },
  data() {
    return {
      firstName: "",
      lastName: "",
      userName: "",
      email: "",
      password: "",
    };
  },
};
</script>

<style lang="scss" scoped>
.form-wrap {
  overflow: hidden;
  display: flex;
  height: 100vh;
  justify-content: center;
  align-self: center;
  margin: 0 auto;
  width: 90%;
  @media (min-width: 800px) {
    width: 100%;
  }

  form {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 0 40px;
    flex: 1;

    .login-register {
      margin-bottom: 20px;

      .router-link {
        color: #000;
      }
    }

    h2 {
      text-align: center;
      font-size: 32px;
      color: #303030;
      margin-bottom: 40px;
      @media (min-width: 800px) {
        font-size: 40px;
      }
    }

    .inputs {
      width: 100%;
      max-width: 350px;
      margin-bottom: 20px;

      .input {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        margin-bottom: 8px;

        input {
          width: 100%;
          border: none;
          background-color: #f2f7f6;
          padding: 4px 4px 4px 30px;
          height: 50px;

          &:focus {
            outline: none;
          }
        }

        .icon {
          position: absolute;
          top: 50%;
          left: 10px;
          transform: translateY(-50%);
          width: 12px;
        }
      }
    }

    .angle {
      display: none;
      position: absolute;
      right: -30px;
      background-color: rgb(255, 255, 255);
      transform: rotateZ(3deg);
      width: 60px;
      height: 105%;
      @media (min-width: 800px) {
        display: initial;
      }
    }
  }

  .background {
    display: none;
    flex: 2;
    background-size: cover;
    background-image: url("../assets/background.png");
    width: 100%;
    height: 100%;
    @media (min-width: 800px) {
      display: initial;
    }
  }
}
</style>
