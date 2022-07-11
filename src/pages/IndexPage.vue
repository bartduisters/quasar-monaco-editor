<template>
  <q-page class="row items-center justify-evenly">
    <div id="editor"></div>
  </q-page>
</template>

<script lang="ts">
import * as monaco from 'monaco-editor';
import { defineComponent, onMounted } from 'vue';

export default defineComponent({
  name: 'IndexPage',
  setup() {
    onMounted(() => {
      const someCode = `
const isBartCool = () => true;
let bartIsCool = isBartCool();
      `;
      monaco.editor.create(document.getElementById('editor') as HTMLElement, {
        value: `// Type your code here\n${someCode}`,
        language: 'typescript',
        theme: 'vs-dark',
        minimap: {
          enabled: false,
        },
      });
    });
    return {};
  },
});
</script>

<style lang="scss">
#editor {
  width: 100%;
  height: 20rem;
}
</style>
