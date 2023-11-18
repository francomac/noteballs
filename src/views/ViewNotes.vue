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

    <NoteCard v-for="note in notes" :key="note.id" :note="note" />
  </div>
</template>

<script setup>
/*
    imports
*/
import { ref } from 'vue'
import uuid4 from 'uuid4'

import NoteCard from '@/components/Notes/NoteCard.vue'

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
