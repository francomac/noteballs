<template>
  <div class="card mb-3">
    <header class="is-hidden card-header">
      <p class="card-header-title">Nota {{ note.id }}</p>
      <button class="card-header-icon" aria-label="more options">
        <span class="icon">
          <i class="fas fa-angle-down" aria-hidden="true"></i>
        </span>
      </button>
    </header>
    <div class="card-content">
      <div class="content">
        {{ note.content }}
      </div>
    </div>
    <footer class="card-footer">
      <a href="#" class="card-footer-item">Edit</a>
      <a href="#" class="card-footer-item">Delete</a>
    </footer>
  </div>
</template>

<script setup>
/*
  props
*/
const props = defineProps({
  note: {
    type: Object,
    required: true
  }
})
</script>

<style scoped></style>
