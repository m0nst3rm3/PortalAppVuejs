<template>
  <div id="portal-form">
    <h2>Register here for Demo</h2>
    <form>
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
          <h4>Country:</h4>
          <select v-model="selected" class="country">
            <option class="country" v-for="country in countries" :key="country" :value="country.value">
              {{ country.label }}
            </option>
          </select>
<!--          <vue-country-code-->
<!--              @onSelect="onSelect" :preferredCountries="['vn', 'us', 'gb']"-->
<!--              :defaultCountry="np"-->
<!--              :enabledFlags=true-->
<!--          />-->
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
          <h4>Gender:</h4>
          <GenderDropDown class="gender-dropdown"/>
        </div>
        <div class="button">
          <button type="submit">Book Your Demo</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
import GenderDropDown from "@/components/genderdropdown";
const countries = require('i18n-iso-countries')
countries.registerLocale(require('i18n-iso-countries/langs/en.json'))

// import Vue from "vue";
// import VueCountryCode from "vue-country-code-select";
//
// Vue.use(VueCountryCode);

export default {
  name: "DemoPortal",
  components: {
    GenderDropDown,
  },
  computed: {
    countries () {
      const list = countries.getNames('en', { select: 'official' })
      return Object.keys(list).map((key) => ({ value: key, label: list[key] }))
    }
  },
  data () {
    return {
      // selected: null
    }
  },
  methods: {
    onSelect({name, iso2, dialCode}) {
      console.log(name, iso2, dialCode);
    },
  }
};

</script>

<style scoped>
#portal-form{
  text-align: center;
}
.forms{
  padding-left: 37%;
  padding-right: 40%;
  text-align: left;
}
.forms-input {
  width: 500px;
  height: 0px;
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
  text-align: left;
}
.button{
  width: 300px;
  height: 50px;
  padding-top: 0.5em;
  text-align: center;

}
/*.gender-dropdown{*/
/*  width: 600px;*/
/*  text-align: Center;*/
/*}*/

.country{
  width: 500px;
  height: 40px;
}

</style>