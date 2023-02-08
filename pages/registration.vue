<template>
  <div class="registration">
    <div class="registration__wrapper">
      <el-form
        :model="form"
        label-width="120px"
        size="large"
        label-position="top"
        class="registration-form"
      >
        <h1 class="registration-form__title">Регистрация</h1>

        <el-form-item>
          <el-input v-model="form.username" placeholder="Введите логин" />
        </el-form-item>

        <el-form-item>
          <el-input v-model="form.password" type="password" placeholder="Введите пароль" />
        </el-form-item>

        <el-form-item>
          <el-input v-model="form.password" type="password" placeholder="Повторите пароль" />
        </el-form-item>

        <el-form-item>
          <el-input v-model="form.password" type="password" placeholder="Введите имя" />
        </el-form-item>

        <el-form-item>
          <el-input v-model="form.password" type="password" placeholder="Введите фамилию" />

          <label class="registration-gender">
            <span>Пол:</span>
            <el-radio-group v-model="form.resource">
              <el-radio label="Мужской" />
              <el-radio label="Женский" />
            </el-radio-group>
          </label>
        </el-form-item>

        <el-form-item>
          <el-button type="primary" class="registration-form__btn">Зарегистрироваться</el-button>
          <el-button class="registration-form__btn" @click="$router.push('/login')">
            Авторизоваться
          </el-button>
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
.registration {
  display: flex;
  justify-content: center;
  margin-top: 45px;
  padding: 0 15px;

  &__wrapper {
    max-width: 400px;
    width: 100%;
    padding: 15px 40px;
    background: #fff;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
  }
}

.registration-form {
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

  &__btn {
    width: 100%;
    margin-left: 0;
    margin-right: 0;

    &:last-child {
      margin-top: 15px;
    }
  }
}

.registration-gender {
  display: flex;
  align-items: center;
  margin-top: 5px;

  span {
    margin-right: 15px;
  }
}
</style>
