<template>
 <v-flex sm8 offset-sm2>
   {{ $store.getters.findStudent(1) }}
    <v-card>
      <v-toolbar dark>
        <v-toolbar-title>Students</v-toolbar-title>
      </v-toolbar>
      <v-list>
        <v-list-tile v-for="(student, index) in $store.getters.students" :to="'editStudent/' + index">
          <v-list-tile-content>
            <v-list-tile-title v-text="student.fullName"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-card>
  </v-flex>
</template>

<script>
import axios from "axios";
import store from "../store.js";
import { mapState } from 'vuex';

export default {
    data() {
        return {

        }
    },
    computed: mapState ({
      students: state =>  state.students
    }),
  async created() {

  }
};
</script>