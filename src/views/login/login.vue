<template>
  <div class="wrapper">
    <img
      src="http://www.dell-lee.com/imgs/vue3/user.png"
      class="wrapper__img"
    >
    <div class="wrapper__input">
      <input
        class="wrapper__input__content"
        placeholder="请输入用户名"
        v-model="username">
    </div>
    <div class="wrapper__input">
      <input
        class="wrapper__input__content"
        placeholder="请输入密码"
        type="password"
        v-model="password">
    </div>
    <div class="wrapper__login-button" @click="handleLogin">登录</div>
    <div class="wrapper__login-link" @click="handleRegisterClick">立即注册</div>
    <Toast v-if="toastData.showToast" :message=toastData.toastMessage />
  </div>
</template>
<script>
import { useRouter } from 'vue-router'
import { reactive, toRefs } from 'vue'
import { post } from '../../../src/utils/request'
import Toast from '../../components/toast'

const useToastEffect = () => {
  const toastData = reactive({
    showToast: false,
    toastMessage: ''
  })
  const showToast = (message) => {
    toastData.showToast = true
    toastData.toastMessage = message
    setTimeout(() => {
      toastData.showToast = false
      toastData.toastMessage = ''
    }, 2000)
  }
  return { toastData, showToast }
}

export default {
  name: 'Login',
  components: { Toast },
  setup () {
    const router = useRouter()
    const data = reactive({ username: '', password: '' })
    const { username, password } = toRefs(data)
    const { toastData, showToast } = useToastEffect()

    const handleLogin = async () => {
      try {
        const result = await post('/api/user/login', {
          username: data.username,
          password: data.password
        })
        // console.log(result)
        if (result?.errno === 0) {
          localStorage.isLogin = true
          await router.push({ name: 'Home' })
        } else {
          showToast('登陆失败')
        }
      } catch (e) {
        alert('请求失败')
      }
    }
    const handleRegisterClick = () => {
      router.push({ name: 'Register' })
    }
    return {
      username,
      password,
      handleLogin,
      handleRegisterClick,
      toastData
    }
  }
}
</script>
<style lang="scss" scoped>
@import "../../style/variables";

.wrapper {
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  transform: translateY(-50%);

  &__img {
    display: block;
    margin: 0 auto .4rem auto;
    width: .66rem;
    height: .66rem;
  }

  &__input {
    height: .48rem;
    margin: 0 .4rem .16rem .4rem;
    background: #F9F9F9;
    border: 1px solid rgba(0, 0, 0, 0.10);
    border-radius: 6px;

    &__content {
      box-sizing: border-box;
      width: 100%;
      line-height: .48rem;
      border: none;
      outline: none;
      background: none;
      padding: 0 .16rem;
      font-size: .16rem;
      color: $content-notice-fontcolor;

      &::placeholder {
        color: $content-notice-fontcolor;
      }
    }
  }

  &__login-button {
    line-height: .48rem;
    margin: .32rem .4rem .16rem .4rem;
    background: #0091FF;
    box-shadow: 0 .04rem .08rem 0 rgba(0, 145, 225, 0.32);
    border-radius: .04rem;
    color: #fff;
    font-size: .16rem;
    text-align: center;
  }

  &__login-link {
    text-align: center;
    font-size: .14rem;
    color: $content-notice-fontcolor;
  }
}
</style>
