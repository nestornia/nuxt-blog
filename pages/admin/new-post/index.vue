<template>
  <div class="admin-new-post-page">
    <section class="new-post-form">
      <AdminPostForm />
    </section>
  </div>
</template>

<script>
import AdminPostForm from '@/components/Admin/AdminPostForm'

export default {
  components: {
    AdminPostForm
  }
}
</script>

<style scoped>
.new-post-from {
  width: 90%;
  margin: 20 auto;
}
.admin-new-post-page {
  display: flex;
  text-align: center;
  align-items: center;
}
</style>