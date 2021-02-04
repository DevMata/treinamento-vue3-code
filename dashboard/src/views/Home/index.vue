<template>
  <CustomHeader @create-account="handleAccountCreate" @login="handleLogin" />
  <Contact/>
  <div class="flex justify-center py-10 bg-brand-gray">
    <p class="font-medium text-center text-gray-800">feedback © 2021</p>
  </div>
</template>

<script>
import { onMounted } from '@vue/runtime-core'
import { useRouter } from 'vue-router'
import Contact from '@/views/Home/Contact'
import CustomHeader from '@/views/Home/CustomHeader'
export default {
  components: { CustomHeader, Contact },
  setup () {
    const router = useRouter()

    onMounted(() => {
      const token = window.localStorage.getItem('token')
      if (token) {
        router.push({ name: 'Feedbacks' })
      }
    })

    function handleLogin () {}

    function handleAccountCreate () {}

    return { handleLogin, handleAccountCreate }
  }
}
</script>
