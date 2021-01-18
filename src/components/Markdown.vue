<template>
  <div>
    <h2>Vue Markdown</h2>
    <div class="d-flex flex-row mt-4" style="height: 400px">
      <textarea
        class="border w-50 me-3 p-3 h-100 rounded"
        :value="text"
        @input="update"
      ></textarea>
      <section class="border w-50 ms-3 p-3" v-html="markedOutput"></section>
    </div>
  </div>
</template>

<script>
import marked from "marked";
import debounce from '@/components/mixins/debounce'
export default {
  mixins:[debounce],
  data() {
    return {
      text: "",
    };
  },
  methods: {
    update(event) {
      const task = () => this.text = event.target.value ;
      this.debounce(task, 500);
    },
  },
  computed: {
    markedOutput() {
      return marked(this.text);
    },
  },
};
</script>

<style>
</style>