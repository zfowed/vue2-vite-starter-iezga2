<template>
  <div class="editor">
    <editor v-model="editorValue" :init="init"></editor>
  </div>
</template>
<script>
import tinymce from 'tinymce/tinymce.js'
// import 'tinymce/models/dom'; (TinyMCE 6)

// 外觀
import 'tinymce/skins/ui/oxide/skin.css'
import 'tinymce/themes/silver'

// Icon
import 'tinymce/icons/default'

// 用到的外掛
import 'tinymce/plugins/emoticons'
import 'tinymce/plugins/emoticons/js/emojis.js'
import 'tinymce/plugins/table'
import 'tinymce/plugins/quickbars'

// 語言包
import 'tinymce-i18n/langs5/zh_TW.js'
// import 'tinymce-i18n/langs/zh_Hans.js' (TinyMCE 6 的簡體中文)

// TinyMCE-Vue
import Editor from '@tinymce/tinymce-vue'

export default {
  components: {
    Editor,
  },
  props: {
    value: {
      type: String,
      default: '',
    },
    plugins: {
      type: [String, Array],
      default: 'quickbars emoticons table',
    },
    toolbar: {
      type: [String, Array],
      default:
        ' bold italic underline strikethrough | fontsizeselect | forecolor backcolor | alignleft aligncenter alignright alignjustify|bullist numlist |outdent indent blockquote | undo redo | axupimgs | removeformat | emoticons |table',
    },
  },
  data() {
    return {
      init: {
        language: 'zh_TW',
        height: 500,
        menubar: false,
        content_css: false,
        skin: false,
        plugins: this.plugins,
        toolbar: this.toolbar,
        quickbars_insert_toolbar: false,
        branding: false,
      },
      editorValue: this.value,
    }
  },
  mounted() {
    tinymce.init({})
  },
  watch: {
    value(newValue) {
      this.editorValue = newValue
    },
    editorValue(newValue) {
      this.$emit('input', newValue)
    },
  },
  methods: {},
}
</script>
