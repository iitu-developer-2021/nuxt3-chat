<template>
  <div class="login">
    <div class="login__wrapper">
      <el-form
        :model="form"
        label-width="120px"
        size="large"
        label-position="top"
        class="login-form"
      >
        <h1 class="login__title">Вход</h1>

        <el-form-item label="Логин" class="login-form__item">
          <el-input v-model="form.username" placeholder="Введите логин" />
        </el-form-item>

        <el-form-item label="Пароль" class="login-form__item no-space">
          <el-input v-model="form.password" type="password" placeholder="Введите пароль" />
        </el-form-item>

        <el-form-item class="login-form__item no-space">
          <div class="login-form__field">
            <el-checkbox-group v-model="form.type">
              <el-checkbox label="Запонить меня" name="type" />
            </el-checkbox-group>
            <NuxtLink to="/forget" class="login-form__forget">Забыли пароль?</NuxtLink>
          </div>
        </el-form-item>

        <el-form-item class="login-form__item">
          <el-button type="primary" class="login-form__btn">Войти</el-button>
          <p class="login-form__text">Впервые на нашем сервисе?</p>
          <el-button class="login-form__btn" @click="$router.push('/registration')"
            >Зарегистрироваться</el-button
          >
        </el-form-item>

        <el-divider class="login-form__divider" />

        <el-form-item class="login-form__item no-space">
          <el-space size="large" alignment="center" class="login-form__socials">
            <el-button class="login-form__btn">
              <img src="~/assets/icons/google.svg" alt="google-icon" />
            </el-button>
            <el-button class="login-form__btn">
              <img src="~/assets/icons/yandex.svg" alt="yandex-icon" />
            </el-button>
            <el-button class="login-form__btn">
              <img src="~/assets/icons/mail.svg" alt="mail-icon" />
            </el-button>
          </el-space>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>
<script lang="ts" setup>
const form = reactive({
  username: '',
  password: '',
})
</script>
<style lang="scss" scoped>
.login {
  display: flex;
  justify-content: center;
  margin-top: 45px;
  padding: 0 15px;

  &__title {
    text-align: center;
    margin-bottom: 16px;
    font-weight: 700;
    font-size: 24px;
    line-height: 33px;
    color: #2c3e50;
    display: inline-block;
    width: 100%;
  }

  &__wrapper {
    max-width: 400px;
    width: 100%;
    padding: 15px 30px;
    background: #fff;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
  }
}

.login-form {
  &__item {
    :deep(label) {
      font-size: 16px;
    }
  }

  &__btn {
    width: 100%;
  }

  &__text {
    text-align: center;
    font-size: 16px;
    line-height: 22px;
    color: #71757a;
    width: 100%;
  }

  &__field {
    display: flex;
    justify-content: space-between;
    width: 100%;
    margin: 9px 0;
  }

  &__forget {
    text-decoration: none;
  }

  &__divider {
    margin: 0 0 5px 0;
  }

  &__socials {
    justify-content: center;
    width: 100%;
    margin: 15px 0;
  }

  &__btn {
    img {
      width: 25px;
      height: 25px;
      cursor: pointer;
    }
  }
}

.no-space {
  margin: 0;
}
</style>
