<template>
  <div>
    <form @submit.prevent="submitForm">
      <label for="em">Email:</label>
      <input type="email" required v-model="email" id="em" />
      <label for="ps">Password:</label>
      <input type="password" required v-model="password" id="ps" />

      <label for="role">Role:</label>
      <select name="" id="role" v-model="role">
        <option value="dev">developer</option>
        <option value="des">designer</option>
      </select>
      <br />
      <label for="check">Accept terms and conditions:</label>
      <input type="checkbox" required v-model="terms" id="check" />
      <br />

      <label>Skills</label>
      <input type="text" v-model="tempSkill" @keyup="addSkill" />

      <div
        class="pill"
        v-for="skill in skills"
        :key="skill"
        @click="delSkill(skill)"
      >
        {{ skill }}
      </div>
      <button>create an account</button>
    </form>

    <p>Email: {{ email }}</p>
    <p>Pass:{{ password }}</p>
    <p>Role: {{ role }}</p>
    <p>terms: {{ terms }}</p>
    <p>skills: {{ skills }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
      role: "des",
      terms: true,
      tempSkill: "",
      skills: [],
    };
  },
  methods: {
    addSkill(e) {
      console.log(e);
      if (e.key === "Alt") {
        if (!this.skills.includes(this.tempSkill)) {
          this.skills.push(this.tempSkill);
        }

        this.tempSkill = "";
        console.log(this.skills);
      }
    },
    delSkill(skill) {
      this.skills = this.skills.filter((el) => {
        return skill !== el;
      });
    },
    submitForm() {
      console.log("prevented");
    },
  },
};
</script>

<style>
form {
  max-width: 420px;
  margin: 30px auto;
  background: 40px;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
  background-color: white;
}
label {
  color: #aaa;
  display: inline-block;
  margin: 25px 0 15px;
  font-size: 0.6em;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}
input {
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #ddd;
  color: #555;
}
.pill {
  display: inline-block;
  margin: 20px 10px 0 0;
  padding: 6px 12px;
  background: #eee;
  border-radius: 20px;
  font-size: 12px;
  letter-spacing: 1px;
  font-weight: bold;
  color: #777;
  cursor: pointer;
}
</style>
