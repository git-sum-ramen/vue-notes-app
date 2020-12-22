<template>
  <div class="note-container">
    <NoteSelectors 
      v-bind:notes="notes"  
      v-bind:selectedNoteId="selectedNoteId" 
      v-on:selectNoteId="selectNote"
    />
    <NoteEditor />
  </div>
</template>

<script>
import NoteSelectors from './NoteSelectors.vue'
import NoteEditor from './NoteEditor.vue'
  export default {
    props: ["notes", "selectedNoteId"],
    components: {
      NoteSelectors,
      NoteEditor
    },
    methods: {
      selectNote: function(note) {
        this.$emit("selectNoteId", note)
      }
    }
  }
</script>