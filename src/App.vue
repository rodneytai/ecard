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

export default {
  name: 'App',
  components: {
      GiftCard,
  }
}
</script>
