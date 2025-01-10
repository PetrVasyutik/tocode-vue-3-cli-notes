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
      notes: [
        {
          title: 'learn vue 3',
          tags: ['work'],
        },
        {
          title: 'Finish course',
          tags: ['work', 'home'],
        },
        {
          title: 'Hello',
          tags: [],
        },
      ]
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
