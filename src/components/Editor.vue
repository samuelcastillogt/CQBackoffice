<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue'
import Quill from 'quill'
import 'quill/dist/quill.snow.css'

const editorRef = ref<HTMLElement | null>(null)
const quill = ref<any>(null)

onMounted(() => {
  if (editorRef.value) {
    quill.value = new Quill(editorRef.value, {
      theme: 'snow',
      modules: {
        toolbar: {
          container: [
            [{ header: [1, 2, false] }],
            ['bold', 'italic', 'underline'],
            [{ list: 'ordered' }, { list: 'bullet' }],
            ['link', 'image']
          ],
          handlers: {
            image: aaa
          }
        }
      }
    })
  }
})

onBeforeUnmount(() => {
  quill.value = null
})
const aaa = ()=> console.log(quill.value.root)
</script>

<template>
  <div>
    <h1>Editor</h1>
    <div ref="editorRef" style="min-height: 300px;"></div>
    <button :onclick="() => aaa()">Guardar</button>
  </div>
</template>

<style scoped>
/* ajustes mínimos para que se vea bien */
.ql-toolbar { border-radius: 4px 4px 0 0; }
.ql-container { border-radius: 0 0 4px 4px; min-height: 200px; }
</style>