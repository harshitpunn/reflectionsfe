<template>
<div>
  <h3>{{ title }}</h3>
  <draggable class="list-group" :list="list" @add="check" @change="checkAdd" group="people">
    <div
      class="list-group-item"
      v-for="(element) in list"
      :key="element.name"
    >
      {{ element.name }}
    </div>
  </draggable>
</div>
</template>

<script lang="ts">
import Vue from 'vue';
import draggable from "vuedraggable";

export default Vue.extend({
  name: 'DraggableComponent',
  props:{
    list: Array,
    title: String
  },
  components: {
    draggable,
  },
  data () {
    return {
      movestatus: true,
    }
  },
  methods: {
    checkAdd (evt) {
      console.log(evt)
    },
    check (evt) {
      console.log(evt)
    }
  }
});
</script>
