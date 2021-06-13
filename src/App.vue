<template>
  <div id="app">
    <div id="nav">
      <Navbar />
    </div>
    <router-view/>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from '@/components/Navbar.vue'

export default {
  components: {
    Navbar
  }
}
</script>


<style lang="scss">
#application {
  max-width: 1440px;
  display: block;
  margin: auto;
}
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.green {
    color: #118C19;
}
.red {
    color: #D9665B;
}
.blue {
    color: #00d2dc;
}
.purple {
    color: #D9665B;
}
.text-bold {
  font-weight: 700;
}
</style>
