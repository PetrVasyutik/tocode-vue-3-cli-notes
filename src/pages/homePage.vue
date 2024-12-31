<template>
  <mainForm @onSubmit="handleSubmit" />
</template>

<script>
import mainForm from '@/components/Notes/mainForm.vue';

export default {
  components: { mainForm},
  methods: {
    handleSubmit (note) {
      console.log(note)
    }
  }
}
</script>
