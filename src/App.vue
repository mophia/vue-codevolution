<script>
export default {
  name: 'App',
  data() {
    return {
      formValues: {
        name: '',
        profileSummary: '',
        country:'',
        jobLocation: [],
        remoteWork: 'no',
        skillSet: [],
        yearsOfExperience: '',
        age: null,
      }
    };
  },
  methods: {
    submitForm(){
      console.log('Form values', this.formValues);
      alert('已经提交以下信息'+JSON.stringify(this.formValues, null, 2))
    }

  }
};
</script>

<template>
  <div>
    <pre>
    {{ JSON.stringify(formValues, null, 2)}}
    </pre>
  </div>

  <form @submit.prevent="submitForm">
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model.lazy.trim="formValues.name">
    </div>

    <br>

    <div>
      <label for="profile">Profile Summary</label>
      <textarea id="profile" cols="30" rows="10" v-model="formValues.profileSummary"></textarea>
    </div>

    <br>

    <div>
      <label for="country">Country</label>
      <select id="country" v-model="formValues.country">
        <option value="">Select a country</option>
        <option value="india">India</option>
        <option value="vietnam">Vietnam</option>
        <option value="singapore">Singapore</option>
      </select>
    </div>

    <br>

    <div>
      <label for="jon-location">job Location</label>
      <select id="job-location" multiple v-model="formValues.jobLocation">
        <option value="india">India</option>
        <option value="vietnam">Vietnam</option>
        <option value="singapore">Singapore</option>
      </select>
    </div>

    <br>

    <div>
      <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no">
      <label for="remoteWork">Open to Remote Work?</label>
    </div>

    <br>

    <div>
      <label>Skill Set</label>
      <input type="checkbox" id="html" value="html" v-model="formValues.skillSet" />
      <label for="html">HTML</label>
      <input type="checkbox" id="css" value="css" v-model="formValues.skillSet"  />
      <label for="css">CSS</label>
      <input type="checkbox" id="javascript" value="javascript" v-model="formValues.skillSet" />
      <label for="javascript">JavaScript</label>
    </div>

    <br>

    <div>
      <label>Years of Experience</label>

        <input type="radio" id="0-2" value="0-2" v-model="formValues.yearsOfExperience"/>
        <label for="0-2">0-2</label>

        <input type="radio" id="3-5" value="3-5" v-model="formValues.yearsOfExperience"/>
        <label for="3-5">3-5</label>
        
        <input type="radio" id="5-10" value="5-10" v-model="formValues.yearsOfExperience"/>
        <label for="5-10">5-10</label>
        
        <input type="radio" id=">10" value=">10" v-model="formValues.yearsOfExperience"/>
        <label for=">10">>10</label>
        
    </div>

    <div>
      <label for="age">Age</label>
      <input type="number" id="age" v-model.number="formValues.age">
    </div>

    <div>
      <button>Submit</button>
    </div>
  </form>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
.underline {
  text-decoration: underline;
}
.promoted {
  font-style: italic;
}
.new {
  color: olivedrab;
}
.sold-out {
  color: red;
}
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}

input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}

input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>