<template>
  <div>
    <h3>Input: {{ title }}</h3>
    <child-component @newValue="changeTitle" />
  </div>
</template>

<script>
import ChildComponent from "./childComponent.vue";

import {ref} from "vue"
export default {
  name: "ParentComponent",
  components: {
    ChildComponent
  },
  setup() {
    const title = ref("");
    const changeTitle = (newTitle) => {
      console.log("fire")
      title.value = newTitle;
    };
    return { title, changeTitle };
  },
};
</script>