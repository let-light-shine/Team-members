<template>
  <div id="hello">
    <div id="nav">
    <!-- <ul id="card"> -->
      <p id="box" v-for="(i,index) in members" v-bind:key="index">
       <br> {{ i.name }} - {{ i.role }}
        <input type="button" id="remove" @click='remove(index)' value="Remove">
       <router-link to="/edit">
       <input type="button" id="edit" @click="send(index)" value="Edit">
       </router-link><br>{{ i.mail }} {{ i.mailID }}
        </p>
        </div>
  </div>
</template>

<style scoped lang="scss">
#hello {
  font-family: 'Source Serif 4', sans-serif;
  text-align: center;
    background-color: #e5e59b;
  height: 3000px;
  width: 100%;
}
#nav {
  padding-left: 20%;
  p {
    padding-left: 30px;
    padding-right: 30px;
    padding-bottom: 7px;
    text-align: left;
    color: #000000;
    font-family: 'Noto Sans', sans-serif;
    font-family: 'Source Serif 4', sans-serif;
    font-size: 22px;
    background-color: #fdffdc;
    width: 75%;
    height: 125px;
  }
}
#smtg{
  padding-top: 10px;
}
#remove, #edit {
  padding-top: 10px;
  background-color: #000505;
  border: none;
  color: #E9DAC1;
  padding: 13px 25px;
  text-align: center;
  text-decoration: none;
  font-size: 18px;
  margin: 3px 2px;
  border-radius: 6px;
  cursor: pointer;
  float: right;
  }
</style>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component({
  methods: {
    remove(index): void {
      this.$store.commit('removeMember', index);
    },
    send(index): void {
      this.$store.commit('saveMember', index);
    },
  },
})
export default class HelloWorld extends Vue {
  members = []

  mounted() {
    this.members = this.$store.getters.getAllMembers;
  }

  computed() {
    this.members = this.$store.getters.getAllMembers;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
