<template>
  <v-container>
    <v-row>
      <v-col cols="12" sm="6" md="6">
        <DraggableComponent :title="userstitle" :list="list1"  />
      </v-col>
      <v-col cols="12" sm="6" md="6">
        <v-row>
          <v-col cols="12" sm="12" md="12">
            <DraggableComponent :title="fetitle" :list="list2"  />
          </v-col>
        </v-row>

        <v-row>
          <v-col cols="12" sm="12" md="12">
            <DraggableComponent :title="betitle" :list="list3"  />
          </v-col>
        </v-row>

        <v-row>
          <v-col cols="12" sm="12" md="12">
            <DraggableComponent :title="qatitle" :list="list4"  />
          </v-col>
        </v-row>

      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue';
import DraggableComponent from "@/components/DraggableComponent"

export default Vue.extend({
  name: 'Home',
  components: {
    DraggableComponent
  },
  data() {
    return {
      qatitle: "QA Specialist",
      betitle: "BE Developer",
      fetitle: "FE title",
      userstitle: "Users",
      list1: [
        { name: "John", id: 1, roles: [] },
        { name: "Joao", id: 2, roles: [] },
        { name: "Jean", id: 3, roles: [] },
        { name: "Gerard", id: 4, roles: [] }
      ],
      list2: [],
      list3: [],
      list4: []
    };
  },
  methods: {
    restrictUsers (role: string) {
      if(role == this.fetitle) {
        this.list2.splice(2)
      }
      else if (role == this.betitle) {
        this.list3.splice(2)
      }
      else if (role == this.qatitle) {
        this.list4.splice(2)
      }
    }
  }
});
</script>
