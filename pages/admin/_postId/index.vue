<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm v-bind:post="loadedPost" />
    </section>
  </div>
</template>

<script>
import AdminPostForm from '@/components/Admin/AdminPostForm'

export default {
  components: {
    AdminPostForm
  },
  data() {
    return {
      loadedPost: {
        author: 'Nestor',
        title: 'My awesome Post',
        content: 'This is greeat',
        thumbnailLink: "data:image/png;base64,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"
      }
    }
  }
}
</script>

<style>
</style>