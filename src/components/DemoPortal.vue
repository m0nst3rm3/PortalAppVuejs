<template>
  <div id="portal-form">
    <h2>Register here for Demo</h2>
    <form @submit= "onSubmit">
      <div class="forms">
        <div>
          <h4>First Name:</h4>
          <input
              class="forms-input"
              type="text"
              name="first_name"
              placeholder="First Name"
              required="required"
          />
          <h4>Last Name:</h4>
          <input
              class="forms-input"
              type="text"
              name="last_name"
              placeholder="Last Name"
              required="required"
          />
          <h4>Gender:</h4>
          <select v-model="gender" class="dropdown">
            <option class="country" v-for="gender in GENDER_CHOICES" :key="gender" :value="gender">
              {{ gender}}
            </option>
          </select>

          <h4>Organization Name:</h4>
          <input
              class="forms-input"
              type="text"
              name="organisation"
              placeholder="Organization Name"
              required="required"
          />
          <h4>Organization Email:</h4>
          <input
              class="forms-input"
              type="email"
              name="email"
              placeholder="***********@aayulogic.com"
              required="required"
          />
          <h4>Organization Size:</h4>
          <select v-model="organization_size" class="dropdown">
            <option class="organization_size" v-for="organization_size in ORGANIZATION_CHOICES"
                    :key="organization_size"
                    :value="organization_size">
              {{ organization_size}}
            </option>
          </select>
          <h4>Country:</h4>
          <select v-model="country" class="dropdown">
            <option class="country" v-for="country in COUNTRIES" :key="country" :value="country">
              {{ country}}
            </option>
          </select>

          <h4>Phone Number:</h4>
          <input
              class="forms-input"
              type="text"
              name="phoneno"
              placeholder="+977 9**********"
              required="required"
          />
          <h4>Domain Name:</h4>
          <input
              class="forms-input"
              type="text"
              name="domain-name"
              placeholder="Domain Name"
              required="required"
          />
        </div>
        <div class="button">
          <button class="c-Button c-Button--close" type="submit">Book Your Demo</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
import {COUNTRIES} from "@/utils/constants"


export default {
  name: "DemoPortal",
  components: {

  },
  data() {
    return {
      COUNTRIES,
      country: 'Nepal',
      GENDER_CHOICES: [('male','Male'), ('Female', "Female"), ('Others', "Others")],
      gender: 'Male',
      ORGANIZATION_CHOICES: [
        ('0-50 Employees', '0-50 Employees'),
        ('51-100 Employees', '51-100 Employees'),
        ('101-150 Employees', '101-150 Employees'),
        ('151-200 Employees', '151-200 Employees'),
        ('201-250 Employees', '201-250 Employees'),
        ('250+ Employees', '250+ Employees'),
      ],
      organization_size: '250+ Employees',
    }
  },

  methods: {
    onSubmit(){
      console.log('form submitted')
    }
  }
};

</script>

<style scoped>
#portal-form {
  text-align: center;
}

.forms {
  padding-left: 37%;
  padding-right: 40%;
  text-align: left;
}

.forms-input {
  width: 500px;
  height: 0px;
  border-radius: 5px;
  border-width: 1px;
  background-color: #f2f2f2;
  padding: 20px;
  text-align: left;
}

.button {
  width: 300px;
  height: 50px;
  padding-top: 0.5em;
  text-align: center;
  size: A4;

}
.dropdown {
  width: 500px;
  height: 45px;
  font-family: Avenir, Helvetica, Arial, sans-serif

}
.c-Button {
  border: none;
  border-radius: 2px;
}
.c-Button--close {
  background-color: aquamarine;
}

</style>