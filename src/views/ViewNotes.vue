<template>
  <div class="notes">
    <div class="card has-background-success-dark p-4 mb-3">
      <div class="field">
        <label class="label">Message</label>
        <div class="control">
          <textarea
            v-model="newNote"
            class="textarea"
            placeholder="Textarea"
            ref="newNoteRef"
          ></textarea>
        </div>
      </div>

      <div class="field is-grouped is-grouped-right">
        <div class="control">
          <button
            @click="addNewNote"
            :disabled="!newNote"
            class="button is-link has-background-success"
          >
            Add New Card
          </button>
        </div>
      </div>
    </div>

    <div v-for="note in notes" :key="note.id" class="card mb-3">
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
  </div>
</template>

<script setup>
import { ref } from 'vue'
import uuid4 from 'uuid4'

const newNote = ref(null)
const newNoteRef = ref(null)

const notes = ref([
  {
    id: 'NT1',
    content: 'some text...'
  },
  {
    id: 'NT2',
    content: 'some some text...'
  }
])

const addNewNote = () => {
  let note = {
    id: 'NT' + uuid4(),
    content: newNote.value
  }

  notes.value.unshift(note)
  newNote.value = null
  newNoteRef.value.focus()
}
</script>
