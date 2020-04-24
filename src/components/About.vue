<template>
  <div id='about'>
    Slabs is awesome!
    <input type="text" v-model="text" />
      <div v-for="user in filteredUsers ">
        <profile :name="user.name" :picture-url="user.pic"></profile>
      </div>
  </div>
</template>

<script>
import Profile from './Profile'

export default {
  name: 'about',
  components: {Profile},
  data: function () {
    return {
      text: '',
      users: [
        {name: 'Jarno', pic: 'https://www.sourcelabs.nl/wp-content/uploads/2018/04/sourcelabs-02-color-square-300x300.jpg'},
        {name: 'Stephan', pic: 'https://www.sourcelabs.nl/wp-content/uploads/2018/06/sourcelabs-01-color-square-experimental-300x300.jpg'},
        {name: 'Arno', pic: 'https://www.sourcelabs.nl/wp-content/uploads/2018/04/sourcelabs-04-color-square-300x300.jpg'},
        {name: 'Francois', pic: 'https://www.biography.com/.image/ar_1:1%2Cc_fill%2Ccs_srgb%2Cg_face%2Cq_auto:good%2Cw_300/MTE5NDg0MDU1NDExNDU5NTk5/after-earth-new-york-premiere---inside-arrivals.jpg'},
        {name: 'Rick', pic: 'https://www.sourcelabs.nl/wp-content/uploads/2018/04/sourcelabs-06-color-square-300x300.jpg'},
        {name: 'Duncan', pic: 'https://www.sourcelabs.nl/wp-content/uploads/2019/12/duncan_Fotor-300x300.jpg'},
        {name: 'Lonneke', pic: 'https://www.sourcelabs.nl/wp-content/uploads/2018/04/sourcelabs-05-color-square-300x300.jpg'}
      ]
    };
  },
  methods: {
    sortSlabbers: function (users) {
      return users.slice().sort((a, b) => { return a.name.localeCompare(b.name) })
    }
  },
  computed: {
    filteredUsers: function () {
      const text = this.text
      return this.sortSlabbers(this.users).filter(function (user) {
        return user.name.toLowerCase().includes(text.toLowerCase())
      })
    }
  }

}
</script>
<!-- styling for the component -->
<style>
  #about {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
