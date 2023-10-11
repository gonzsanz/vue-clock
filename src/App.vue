<template>
  <div>
    <VueClock :theme="selectedColor" />
    <div class="color">
      <input type="color" v-model="selectedColor">
    </div>
  </div>
</template>


<script>
import VueClock from './components/VueClock.vue'
export default {
  components: { VueClock },
  data() {
    return {
      selectedColor: 'red'
    }
  },
}

</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@500&family=Orbitron:wght@400;800&family=Poppins:wght@400;500;700&display=swap');

body {
  background-color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
}

input {
  cursor: pointer;
  position: absolute;
  top: 1rem;
  left: 30rem;
}
</style>
