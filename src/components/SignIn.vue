<script setup lang="ts">
import { ref } from 'vue';

const email = ref('');
const password = ref('');
</script>

<template>
  <div class="form-wrap">
    <form class="login">
      <p class="login-register">
        还没有账号？
        <NuxtLink to="/register" class="router-link">新用户注册</NuxtLink>
      </p>
      <h2>登录Roller</h2>
      <div class="inputs">
        <div class="input">
          <input v-model="email" type="email" placeholder="Email" />
          <Email class="icon" />
        </div>
        <div class="input">
          <input v-model="password" type="password" placeholder="Password" />
          <Password class="icon" />
        </div>
      </div>
      <NuxtLink class="forgot-password" to="forgotPassword">
        忘记密码
      </NuxtLink>
      <button>登录</button>
      <div class="angle"></div>
    </form>
    <div class="background"></div>
  </div>
</template>

<style lang="scss">
.form-wrap {
  overflow: hidden;
  display: flex;
  height: 100vh;
  justify-content: center;
  align-content: center;
  margin: 0 auto;
  width: 90%;

  @media (min-width: 900px) {
    width: 100%;
  }

  .login-register {
    margin-bottom: 32px;

    .router-link {
      color: #000;
    }
  }

  form {
    padding: 0 10px;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 1;

    @media (min-width: 900px) {
      padding: 0 50px;
    }

    h2 {
      text-align: center;
      font-size: 32px;
      color: #303030;
      margin-bottom: 40px;
      @media (min-width: 900px) {
        font-size: 48px;
      }
    }

    .inputs {
      width: 100%;
      max-width: 350px;

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
          width: 12px;
          position: absolute;
          left: 10px;
        }
      }
    }

    .forgot-password {
      text-decoration: none;
      color: #000;
      cursor: pointer;
      font-size: 14px;
      margin: 16px 0 32px;
      border-bottom: 1px solid transparent;
      transition: 0.5s ease all;

      &:hover {
        border-color: #303030;
      }
    }

    .angle {
      display: none;
      position: absolute;
      background-color: #fff;
      transform: rotateZ(3deg);
      width: 60px;
      right: -30px;
      height: 101%;

      @media (min-width: 900px) {
        display: initial;
      }
    }
  }

  .background {
    display: none;
    flex: 2;
    background-size: cover;
    background-image: url('@/static/assets/bg.png');
    width: 100%;
    height: 100%;
    @media (min-width: 900px) {
      display: initial;
    }
  }
}
</style>
