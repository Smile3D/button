<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <GeneralButton
        type="button"
        customBackgroundColor="blue"
        hoverBackgroundColor="#000"
        customColor="#f00"
        hoverColor="blue"
        border="1px solid red"
        borderRadius="10px"
        minHeight="50px"
        minWidth="200px"
        fontSize="20px"
        fontWeight="600"
        @onClick="test"
    >
      Сохранить
    </GeneralButton>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import GeneralButton from '@/components/GeneralButton'

export default {
  name: 'Home',
  components: {
    HelloWorld,
    GeneralButton
  },
  methods: {
    test() {
      console.log(111)
    }
  }
}
</script>
