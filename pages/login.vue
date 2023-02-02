<template>
  <div class="login">
    <el-card class="login__wrapper">
      <h2 class="login__title">Авторизация</h2>
      <el-form ref="form" class="login-form">
        <el-form-item prop="username">
          <el-input placeholder="Username" :prefix-icon="User"> </el-input>
        </el-form-item>
        <el-form-item prop="password">
          <el-input placeholder="Password" type="password" :prefix-icon="Lock"></el-input>
        </el-form-item>
        <el-form-item>
          <el-button class="login-form__button" type="primary" native-type="submit" block>
            Login
          </el-button>
        </el-form-item>
        <a class="login-form__forgot-password" href="https://oxfordinformatics.com/"
          >Forgot password ?</a
        >
      </el-form>
    </el-card>
  </div>
</template>

<script lang="ts" setup>
import { User, Lock } from '@element-plus/icons-vue'
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$teal: rgb(0, 124, 137);

.login {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 50px;

  &__title {
    font-family: 'Open Sans', Roboto, sans-serif;
    letter-spacing: 1px;
    padding-bottom: 20px;
    text-align: center;
  }
}

.login-form {
  width: 330px;

  &__button {
    width: 100%;
    margin-top: 40px;
  }

  &__forgot-password {
    color: $teal;
    margin-top: 10px;
    text-decoration: none;
    text-align: center;
    display: inline-block;
    width: 100%;

    &:hover,
    &:active,
    &:focus {
      color: lighten($teal, 7);
    }
  }

  .el-input__inner:hover {
    border-color: $teal;
  }

  .el-button--primary {
    background: $teal;
    border-color: $teal;

    &:hover,
    &.active,
    &:focus {
      background: lighten($teal, 7);
      border-color: lighten($teal, 7);
    }
  }

  .el-card {
    width: 340px;
    display: flex;
    justify-content: center;
    padding-top: 0;
    padding-bottom: 30px;
  }
}
</style>
