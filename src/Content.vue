<template>
  <div class="comp-content">
    <div v-for="(task, idx) in filter_task" :key="idx">
        <input type="checkbox"><span>{{ task.task }}</span>
    </div>

  </div>
</template>

<script>
export default {
  name: 'content',
  data () {
    return {
      tasks: [ 
          {"task_id":0, "is_checked": false, "label_id": 0, "task": "Take care of home"},
          {"task_id":1, "is_checked": false, "label_id": 2, "task": "Some procedure to give birth"},
          {"task_id":2, "is_checked": false, "label_id": 0, "task": "Take a deep breath"},
          {"task_id":3, "is_checked": false, "label_id": 1, "task": "Watching something fun"},
          {"task_id":4, "is_checked": false, "label_id": 1, "task": "Do nothing"},
          {"task_id":5, "is_checked": false, "label_id": 0, "task": "Clear data"},
          {"task_id":6, "is_checked": false, "label_id": 1, "task": "Go to a dept. store and buy something"}
        ],
      label_id: null
    }
  },
  methods: {
    filter_by_label (label_id) {
      this.label_id = label_id;
    }
  },
  computed: {
    filter_task: function() {
      if (this.label_id == null) {
        return this.tasks
      } else {
        let label_id = this.label_id;
        return this.tasks.filter ( (task) => { return task['label_id'] == label_id })
      }
    }
  },
  created () {
    let master_tasks= [
    ]
    return master_tasks
    this.tasks = master_tasks;
  },
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
