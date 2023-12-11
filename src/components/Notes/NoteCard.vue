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
        <div class="has-text-right has-text-grey-light mt-2">
          <small>{{ characterLength }}</small>
        </div>
      </div>
    </div>
    <footer class="card-footer">
      <a href="#" class="card-footer-item">Edit</a>
      <a @click.prevent="handleDeleteClick" href="#" class="card-footer-item"
        >Delete</a
      >
    </footer>
  </div>
</template>

<script setup>
/*
  imports
*/
import { computed, defineEmits } from 'vue'
/*
  props
*/
const props = defineProps({
  note: {
    type: Object,
    required: true
  }
})
/*
  emits
*/
const emit = defineEmits(['deleteClicked'])

/*
  characterLength
*/
const characterLength = computed(() => {
  let length = props.note?.content.length
  let description = length > 1 ? 'characters' : 'character'
  return `${length} ${description}`
})

const handleDeleteClick = () => {
  emit('deleteClicked', props.note?.id)
}
</script>

<style scoped></style>
