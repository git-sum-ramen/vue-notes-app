<template>
  <div class="note-selectors">
    <NoteSelector 
      v-for="note in notes" 
      v-bind:key="note.id" 
      v-bind:note="note"       
      v-bind:selectedNoteId="selectedNoteId"    
      v-on:selectNoteId="selectNote"   
    />
  </div>
</template>

<script>
import NoteSelector from './NoteSelector.vue'
export default {
  props: ["notes", "selectedNoteId"],
  components: {
    NoteSelector
  },
  data: function() {
    return {
      
    }
  },
  methods: {
    selectNote: function(note) {
      console.log('selecting note in parent...')
      this.$emit("selectNoteId", note)
      // this.selectedNoteId = note.id;
    }
  }
}
</script>