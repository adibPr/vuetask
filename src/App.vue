<template>
  <div class="app">
    <div class="navbar">
      <Navbar />
    </div>
    <div class="label" >
      <Label @filter="filter_by_label" />
    </div>
    <div class="content">
      <Content ref="content"/>
    </div>
  </div>
</template>

<script>
import Navbar from './Navbar.vue'
import Label from './Label.vue'
import Content from './Content.vue'

export default {
  name: 'app',
  components: {
    Navbar,
    Label,
    Content
  },
  data () {
    return {
    }
  },
  methods: {
    filter_by_label (payload){
      this.$refs.content.filter_by_label (payload['label_id'])
    }
  }
}
</script>
<style scoped>
  .app {
    background-color:#edf5e1;
    display: grid;

    grid-template-columns:repeat(10, 10%);
    /*grid-template-columns: 40px 50px auto 50px 40px;*/
    grid-template-rows: 10% auto;
    justify-items: stretch;
  }

  .navbar {
    grid-column: 1 / 11;
    grid-row: 1;
  }

  .label {
    grid-row: 2;
    grid-column: 3/4;
  }

  .content {
    grid-row: 2;
    grid-column: 4/11;
  }

</style>
