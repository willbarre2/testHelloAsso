<template>
  <div id="cards-container">
    <Cards/>
  </div>
</template>

<script>
// @ is an alias to /src
import Cards from '@/components/Cards.vue'

export default {
  name: 'Home',
  components: {
    Cards
  }
}
</script>

<style lang="scss">
#cards-container{
  max-width: 1400px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
