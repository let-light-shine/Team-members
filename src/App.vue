<template>
<div class="height">
  <div id="app" class="height max-h-full">
    <div id="nav">
      <div id="smtg2">
      <h2><router-link to="/">Team Members</router-link></h2>
      </div>
      <div id="smtg">
      <router-link to="/invite">
      <input type="button" class="button" value="Invite Member"></router-link>
      </div>
    </div>
    <router-view/>
  </div>
  </div>
</template>

<style lang="scss">
.height{
    background-color: #e5e59b;
    height: 100%;
}
#app {
  font-family: 'Source Serif 4', sans-serif;
    background-color: #e5e59b;
  text-align: center;
  text-decoration: none;
  color: #000000;
  width: 100%;
  height: 100%;
}
.button{
  background-color: #000000;
  border: none;
  color: #FBF8F1;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  font-size: 16px;
  margin: 4px 2px;
  border-radius: 8px;
  cursor: pointer;
  float: right;
  }
#nav {
  padding: 40px;
  a {
    font-weight: bold;
    color: #000000;
    text-decoration: none;
    font-size: 40px;
    //padding-left: 100px;
  }
  #smtg2{
    float: left;
    padding-left: 19%;
    font-family: 'Source Serif 4', sans-serif;
    color: #54BAB9;
    text-decoration: none;
  }
  #smtg{
    padding-top: 18px;
    padding-right: 236px;
    font-family: 'Source Serif 4', sans-serif;
    float: right;
  }
}
</style>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

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
