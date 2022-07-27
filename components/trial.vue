<!-- <template>
  <div>
    <form @submit.prevent="customSubmit">
      <label>Name</label>
      <input type="text" required v-model="user.name" id="name">
      <label>E-mail:</label>
      <input type="email" required v-model="user.email" id="email">
      <label>Mobile Number</label>
      <input type="number" required v-model="user.number" id="number">
    </form>

    <button type="submit" class=buttonSignup @click="customSubmit">Submit</button>
    <br/>
    You typed:<br/>
    name: {{user.name}}<br/>
    email: {{user.email}}<br/>
    number: {{user.number}}

  </div>
</template>

<script>
export default {
  data() {
    return {
      users: [],

      user: {
        name: '',
        email: '',
        number: ''
      }
    };
  },
  methods: {


    customSubmit() {
      // do some checking here
      this.users.push(this.user)
      this.user = {name:'', email:'', number:''};
      console.log(this.users)

    },


  }
}
</script> -->