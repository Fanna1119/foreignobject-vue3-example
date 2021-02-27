<template>
  <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
    <polygon points="5,5 195,10 185,185 10,195" />
    <foreignObject
      :x="foreignobjdata.x"
      :y="foreignobjdata.y"
      :width="foreignobjdata.width"
      :height="foreignobjdata.height"
    >
      <div xmlns="http://www.w3.org/1999/xhtml">
        <p>{{ textobj }}</p>
        <slot></slot>
        <p>
          {{ outsidetext }}
        </p>
      </div>
    </foreignObject>
    {{ foreignobjdata }}
  </svg>
</template>

<script>
import { computed, reactive, ref, toRefs } from "vue";
export default {
  props: {
    outsidetext: {
      type: String,
    },
  },
  setup(props) {
    const foreignobjdata = reactive({
      x: 20,
      z: 20,
      width: 160,
      height: 160,
    });

    const textobj = ref("helloworld");

    const { outsidetext } = toRefs(props);

    return {
      textobj,
      outsidetext,
      foreignobjdata,
    };
  },
};
</script>

<style scoped>
div {
  color: white;
  font: 18px serif;
  height: 100%;
  overflow: auto;
}
</style> 