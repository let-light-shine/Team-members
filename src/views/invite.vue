<template>
  <div id="invite">
    <div id="card">
  <p id="line1"><br>Invite a team member to use Chargebee
    </p>
    <hr>
  <p id="line2">
You can either let your team members access everything in this site or assign specific roles to them
  </p>
  <p id="textbox">
    <span class="tab"></span>
    <span class="tab"></span>
  <label> Name       </label>
  <textarea v-model="name"> </textarea>
  <span class="tab"></span>
  <span class="tab"></span>
  <span class="tab"></span>
  <label>Email        </label>
<textarea v-model="mail">
  sample@chargebee.com
  </textarea>
  </p>
  <div>
  <p id="useraccess">Select user level access</p>

  <div class="options">
  <input type="radio" id="0" v-model="role" name="role" value="Admin"> <label for="0">
  <span><b>Admin</b> </span>
  </label><br>
  </div>

  <div class="options">
  <input type="radio" id="1" v-model="role" name="role" value="Support">
  <label for="1"><span><b> Support</b> </span></label><br>
  </div>

  <div class="options">
  <input type="radio" id="2" v-model="role" name="role" value="Analyst">
  <label for="2"><span> <b> Analyst</b> </span>  </label>
  </div>
  <br>
   <input type="submit" id="invitebutton" value="Invite Member" @click='addMember'>
  <input type="button" id="cancel" value="Cancel" @click="cancel">
  </div>
    </div>
  </div>
</template>

<style scoped lang="scss">

#invite{
  padding-top: 40px;
    padding-left: 200px;
    font-family: 'Noto Sans', sans-serif;
font-family: 'Playfair Display', serif;
font-family: 'Source Serif 4', sans-serif;
font-size:17px;
height:1500px;
}
#line1{
    color:#000000;
    text-align: center;
    font-size:25px;
}

#line2{
    color:#000000;
    text-align: center;
    font-size:19px;
}
hr {
    border: none;
    border-top: 1px double #333;
    color: #333;
    overflow: visible;
    text-align: center;
    height: 5px;
    width:90%;
}
#textbox{
    text-align:left;
    padding-left: 100px;
}
#useraccess{
    text-align: left;
    padding-left: 77px;
    font-size:19px;
}
.tab {
    display: inline-block;
    margin-left: 40px;
}
.options{
    text-align: left;
    padding-left: 100px;
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
#invitebutton, #cancel {
  background-color: #000000;
  border: none;
  color: white;
  padding: 12px 20px;
  text-align: right;
  text-decoration: none;
  font-size: 14px;
  font:bold;
  margin: 4px 2px;
  border-radius: 8px;
  cursor: pointer;
  float: center;
  }
#card{
  background-color: #fdffdc;
  width: 80%;
  height: 500px;
h1{
  padding-top: 0px;
}
}
</style>
<script>
import { Component, Vue } from 'vue-property-decorator';

@Component({
  data() {
    return {
      name: '',
      role: '',
      mail: '',
    };
  },
  methods: {
    addMember() {
      this.$store.commit('setNewMember', { name: this.name, role: this.role, mail: this.mail });
      this.$router.push('/');
    },
    cancel() {
      this.$router.push('/');
    },
  },
})
export default class InviteMembers extends Vue {}
</script>
