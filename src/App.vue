<template>
  <div class="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('Zelda')">change name</button>
    <button @click="changeAge(30)">change age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from "vue";

export default defineComponent({
  name: "App",
  components: {},
  setup() {
    // const state = reactive({
    //   name: "Link",
    //   age: 25 as number,
    // });

    // state.name = 999 // cannnot change type

    // return {
    //   ...toRefs(state),
    // };

    const name = ref("Link");
    const age = ref<number>(25);

    return {
      name,
      age,
    };
  },
  methods: {
    changeName(name: string) {
      this.name = name;
      return name;
    },
    changeAge(age: number) {
      this.age = age;
      return age;
    },
  },
});
</script>

<style></style>
