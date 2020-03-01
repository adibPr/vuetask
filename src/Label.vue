<template>
  <div class="comp-label">
    Projects 
    <br>
    <ul>
      <li v-for="(label, idx) in label" :key="idx">
        <a href="#" @click="filter(label.id)">{{ label.name }} <sup class="total">{{ label.total }}</sup></a>
      </li>
    </ul>

  </div>
</template>

<script>
export default {
  name: 'label',
  data () {
    return {
      "label": [
        {"id": null, "name": "All", "total": 10},
        {"id": 0, "name": "Work", "total": 10},
        {"id": 1, "name": "Business", "total": 4},
        {"id": 2, "name": "College", "total": 0}
      ]
    }
  },
  methods: {
    filter (label_id){
      this.$emit ("filter", { "label_id": label_id });
    }
  }
}
</script>

<style scoped>

  .comp-label{
    padding-top: 1em;
  }

  ul {
    list-style-type:none; /* remove bullets */
    padding-left: 2em;
  }

  li a {
    color: black;
    display: block;
    text-decoration: none; /* remov underline link */
    margin-top: 0.5em;
    margin-bottom: 0.5em;
  }

  a:hover {
    background-color:#8ee4af;
  }

  .total {
    font-size:0.5em;
    color: gray;
    text-align: center;
  }

</style>
