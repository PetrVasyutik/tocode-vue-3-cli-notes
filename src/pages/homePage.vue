<template>
  <mainForm @onSubmit="handleSubmit" />
  <mainList @onRemove="handleRemove" :items="notes"/>
</template>

<script>
import mainForm from '@/components/Notes/mainForm.vue';
import mainList from '@/components/Notes/mainList.vue';

export default {
  components: { mainForm, mainList },
  data() {
    return {
      notes: ['task 1', 'task 2','task 3']
    }
  },
  methods: {
    handleSubmit(note) {
      this.notes.push(note)
    },
    handleRemove(index) {
      this.notes.splice(index, 1)
    }
  }
}
</script>
