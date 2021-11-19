<template>
 <custom-header
  @create-account="handleAccountCreate"
  @login="handleLogin"
 />

</template>

<script>
import { onMounted } from 'vue'
import { useRouter } from 'vue-router'
import CustomHeader from './CustomHeader.vue'
import Contact from './Contact.vue'

export default {
  components: { CustomHeader, Contact },
  setup() {
    const router = useRouter()

    onMounted(() => {
      const token = window.localStorage.getItem('token')
      if(token){
        router.push({ name:'Feedbacks' })
      }
    })

    function handleLogin() {
    }

    function handleAccountCreate(){
    }

    return {
      handleLogin,
      handleAccountCreate
    }
  }
}
</script>
