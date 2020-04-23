<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <vue-ctk-date-time-picker
      v-model="theDate"
      :name="'Date'"
      :format="'YYYY-MM-DD'"
      :formatted="'DD MMM, YYYY'"
      :only-date="true"
      :data-vv-as="'date'"
      :first-day-of-week="1"
      :range="true"
    ></vue-ctk-date-time-picker>
  </div>
</template>

<script>
import "vue-ctk-date-time-picker/dist/vue-ctk-date-time-picker.css";
import moment from "moment";

export default {
  name: "HelloWorld",
  components: {
    "vue-ctk-date-time-picker": () =>
      import(/* webpackChunkName: "vue-ctk-date-time-picker" */ "vue-ctk-date-time-picker")
  },
  props: {
    msg: String
  },
  data() {
    return {
      theDate: moment().format("YYYY-MM-DD")
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
