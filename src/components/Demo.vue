<template>
  <tinycme-editor v-model="editorData"></tinycme-editor>
</template>

<script>
import TinycmeEditor from './tinymce.vue'

export default {
  components: {
    TinycmeEditor,
  },
  data() {
    return {
      editorData: '<p>Content of the editor.</p>',
    }
  },
  watch: {
    editorData: {
      immediate: false,
      handler(newValue) {
        console.log(newValue)
      },
    },
  },
}
</script>
