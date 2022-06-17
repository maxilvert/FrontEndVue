<template>
  <div class="hello">
    <div id="app">
      <div class="container">
        <div class="justify">
          <div class="col1">
            <div class="card">
              <div class="card-header">Vue Axios - EDUCBA.COM</div>
              <div class="card-body">
                <form @submit="formSubmit">
                  <div class="form-control">
                    <label>email</label>
                    <input type="text" v-model="email" name="email" placeholder="Enter Your email" />
                  </div>
                    <div class="form-control">
                    <label>Name</label>
                    <input type="text" v-model="name" name="name" placeholder="Enter Your Name" />
                  </div>
                    <div class="form-control">
                    <label>Surname</label>
                    <input type="text" v-model="surname" name="surname" placeholder="Enter Your surname" />
                  </div>
                   <div class="form-control">
                    <label>Role</label>
                    <input type="text" v-model="role" name="role" placeholder="Enter Your role" />
                  </div>
                   <div class="form-control">
                    <label>Password</label>
                    <input type="text" v-model="password" name="password" placeholder="Enter Your password" />
                  </div>
                  <div class="form-control">
                    <label>Parain</label>
                    <input type="text" v-model="parain" name="parain" placeholder="Enter Your parain" />
                  </div>
                  
                  <input type="submit" value="Save Information" class="btn btn-block" />
                </form>
                <strong>Result:</strong>
                <pre>
{{ output }}
</pre>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios';
export default {

  mounted() {
    console.log('Component mounted.')
  },
  data() {
    return {
      email: '',
      name: '',
      surname: '',
      role: '',
      password: '',
      parain: '',
      result: ''
    };
  },
  methods: {
    formSubmit(e1) {
      e1.preventDefault();
      let currentObj = this;
          const data = {
    		email: console.log(this.email) ,
        name: this.name,
        surname: this.surname,
        role: this.role,
        password: this.password,
        parain: this.parain,
    	};
  
      /*axios.patch('http://localhost:3000/users/1', data)
        .then(function (response) {
          currentObj.output = response.data;
        })
        .catch(function (error) {
          currentObj.output = error;
        });*/
      axios('http://localhost:3000/users/1', {
        method: 'HEAD',
        mode: 'no-cors',
    }).then((response) => {
        console.log(response);
    }).catch((e) => {
        console.log(e);
    });  
    }
  }
}
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
