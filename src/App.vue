<template>
  <div>
    <foreign outsidetext="🔥prop from parent🔥">
      <p>{{ slottext }}</p>
    </foreign>
  </div>

  <input v-model="slottext" type="text" />
</template>

<script>
import { ref } from "vue";
import foreign from "./components/foreign.vue";

export default {
  name: "App",
  components: {
    foreign,
  },

  setup() {
    const slottext = ref("hello");

    return {
      slottext,
    };
  },
};
</script>
