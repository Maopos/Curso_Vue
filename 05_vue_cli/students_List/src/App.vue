<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <div class="container">
      <div class="form">
        <div class="form-group">

          <br>
          <label>Name</label>
          <input type="text" v-model="students.name" class="form-control" id="name" placeholder="Enter name">
          <br>
        </div>

        <div class="form-group">
          <label>School</label>
          <input type="text" v-model="students.school" class="form-control" id="name" placeholder="Enter school">
          <br>
        </div>

        <div class="form-group">
          <label>Phone</label>
          <input type="email" v-model="students.phone" class="form-control" id="email" placeholder="Enter phone number">
          <br>
        </div>

        <button class="btn btn-primary" @click="addStudent">Guardar</button>
        <br>
        <br>
        <div class="row">
          <div class="col-md-5" v-for="index in registry">
              <div class="card">
                <h2>{{index.name}}</h2>
                <h2>{{index.school}}</h2>
                <h2>{{index.phone}}</h2>
              </div>
              <br>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      title: 'Students List',
      students: {
        name: '',
        school: '',
        phone: ''
      },
      registry: [
        
      ]
    }
  },
  methods: {
    addStudent: function() {
      const { name, school, phone } = this.students;
      this.registry.push({
        name,
        school,
        phone
      });

    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
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
