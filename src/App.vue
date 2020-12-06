<template>
    <div id="app">
        <GiftCard/>
    </div>
</template>

<script>
import GiftCard from './components/GiftCard.vue';
// npm install materialize-css@next
import '../node_modules/materialize-css/dist/css/materialize.min.css';
import '../node_modules/materialize-css/dist/js/materialize.min.js';
//npm install vue bootstrap-vue bootstrap
// import 'bootstrap/dist/css/bootstrap.css'
// import 'bootstrap-vue/dist/bootstrap-vue.css'

export default {
  name: 'App',
  components: {
      GiftCard,
  }
}
</script>
