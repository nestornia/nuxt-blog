<template>
  <form @submit.prevent="onSave">
    <AppControlInput v-model="editedPost.author">Author Name</AppControlInput>
    <AppControlInput v-model="editedPost.title">Title</AppControlInput>
    <AppControlInput v-model="editedPost.thumbnailLink">Thumbnail Link</AppControlInput>
    <AppControlInput control-type="textarea" v-model="editedPost.content">Content</AppControlInput>
    <AppButton type="submit">Save</AppButton>
    <AppButton type="button" style="margin-left: 10px" btn-style="cancel" @click="onCancel">Cancel</AppButton>
  </form>
</template>

<script>
import AppControlInput from '@/components/UI/AppControlInput'
import AppButton from '@/components/UI/AppButton'

export default {
  data() {
    return {
      editedPost: this.post ? { ...this.post } : {
        author: '',
        title: '',
        thumbnailLink: '',
        content: ''
      }
    }
  },
  props: {
    post: {
      type: Object,
      required: false
    }
  },
  methods: {
    onSave() {
      //save the post
      console.log(this.editedPost)
    },
    onCancel() {
      //navigate back
      this.$router.push('/admin')
    }
  },
  components: {
    AppControlInput,
    AppButton
  }
}
</script>