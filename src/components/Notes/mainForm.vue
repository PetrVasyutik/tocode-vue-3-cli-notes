<template>
  <div class="note-form__wrapper">
    <form class="note-form" @submit.prevent="onSubmit">
      <textarea
        required
        v-model="value"
        placeholder="Type or note"
      />
      <tagList @onItemClick="handleClick" :items="tags" />
      <button class="btn btnPrimary" type="submit">Add new note</button>
    </form>
  </div>
</template>

<script>
import tagList from "@/components/Ui/tagList.vue"
export default {
  components: {tagList},
  data() {
    return {
      value: '',
      tags: ['home', 'work', 'travel']
    }
  },
  methods: {
    onSubmit () {
      this.$emit('onSubmit', this.value)
      this.value = ''
    },
    handleClick(tag) {
      console.log(tag)
    }
  }
}
</script>
<style lang="scss">

.note-form__wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.note-form {
  display: flex;
  flex-direction: column;
  max-width: 100%;
  width: 600px;

  textarea {
    margin-bottom: 0;
  }
}
</style>
