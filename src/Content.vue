<template>
  <div class="comp-content">
    <div v-for="(task, idx) in tasks" :key="idx">
        <input type="checkbox"><span>{{ task.task }}</span>
    </div>

  </div>
</template>

<script>
export default {
  name: 'content',
  data () {
    return {
      tasks: [ ]
    }
  },
  created () {
    this.filter_by_label (null);
  },
  methods: {
    filter_by_label: function (label_id) {
      let master_tasks= [
            {"label_id": 0, "task": "Take care of home"},
            {"label_id": 2, "task": "Some procedure to give birth"},
            {"label_id": 0, "task": "Take a deep breath"},
            {"label_id": 1, "task": "Watching something fun"},
            {"label_id": 1, "task": "Do nothing"},
            {"label_id": 0, "task": "Clear data"},
            {"label_id": 1, "task": "Go to a dept. store and buy something"}
      ]
      if (label_id == null) {
        this.tasks = master_tasks
      } else {
        console.log ("over here")
        this.tasks = master_tasks.filter (function (e) { return e['label_id'] == label_id })
      }
    }
  }
}
</script>

<style scoped>
  .comp-content {
    padding-top: 1em;
    padding-left: 2em;
  }

  input[type="checkbox"] {
    margin-right: 1em;
    margin-top: 0.25em;
    margin-bottom: 0.25em;
  }


</style>
