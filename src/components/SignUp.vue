<template>
  <form>
    <label for="">Email</label>
    <input type="email" required v-model="email">

    <label for="">Password</label>
    <input type="password" required v-model="password">

    <label for="">Roles:</label>
    <select v-model="role">
      <option value="developer">Web Developer</option>
      <option value="designer">Web Designer</option>
    </select>

    <div>
      <label for="">Skills</label>
      <input type="text" @keyup="addSkill" v-model="skill">
      <p>{{ skills }}</p>
    </div>
    <div>
      <input type="checkbox" required v-model="accept">
      <label for="">Accept Terms and Conditions</label>
    </div>

    

  </form>
  <p>Email - {{email}}</p>
  <p>Password - {{password}}</p>
  <p>Role - {{role}}</p>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      password: '',
      role: '',
      accept: false,
      skills:[],
      skill: "",
    }
  },
  methods: {
    addSkill(e) {
      if(e.key===","){
        this.skills.push(this.skill)
        this.skill = "";
      }
    }
  },
}
</script>

<style>
    form {
        max-width: 420px;
        margin: 30px auto;
        background: white;
        text-align: left;
        padding: 40px;
        border-radius: 10px;
    }
    label{
        coolor: #aaa;
        display: inline-block;
        margin: 25px 0 15px;
        font-size: 0.6rem;
        text-transform: uppercase;
        letter-spacing: 1px;
        font-weight: bold;
    }
    input, select{
        display: block;
        padding: 10px 6px;
        width: 100%;
        border: none;
        border-bottom: 1px solid #ddd;
        color: #555;
    }
    input[type="checkbox"] {
        display: inline-block;
        width: 16px;
        margin: 0 10px 0 0;
        position: relative;
    }
</style>