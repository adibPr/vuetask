<template>
  <div class="container">
    <div class="box1">
      <a href="#"><i class="fab fa-vuejs" style="font-size: 2em;"></i></a>
    </div>
    <div class="box2">
      <input type="text" class="form-control" id="search" placeholder="Search ">
    </div>
    <div class="box3">
      <button for="search" type="button"><i class="fa fa-search"></i></button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'navbar',
  data () {
    return {
    }
  }
}
</script>

<style scoped>

  /*
    color1: #05386b
    color2: #379683
    color3: #5cdb95
    color4: #8ee4af
    color5: #edf5e1
  */
  .container {
    display: grid;
    padding-top: 0.5em;
    grid-template-columns: 20% 15% 25% 10% 30%;
    grid-template-rows: 10% auto;
    justify-items: stretch;


    /*background-color: #8ee4af;*/
    margin: auto;
    max-width: inherit;
  }

  .box1 {
    margin: 0px;
    padding: 0px;
    grid-column: 1;
    justify-self: right;
    align-self: center;
  }

  .box2 {
    grid-column: 3;
  }

  .box3 {
    grid-column: 4;
    justify-self: left;
    margin-left: 1em;
  }


  input[type=text] {
    vertical-align:middle;
    box-sizing:border-box;
    margin-top: 0px;
    padding-top: 0px;
    background-color: #edf5e1;
  }

  button[type="button"] {
    background-color: #05386b;
    border-color:#05386b;
    color: white;
    height: 100%;
  }
    

</style>
