<template>
  <div>
    <Navbar />
    <h3>{{firstName + lastName}}</h3>
    <div v-for="(data, index) in filterScore" :key="index" >
      <h4>{{data.score}}</h4>
    </div>
  <h5>{{count}}</h5>
  <button @click="addCount">Penceet</button>
  <button @click="minCount">Kurangi</button>
  <div>
    <h4>{{email}}</h4>
    <h4>{{password}}</h4>
    <h4>{{age}}</h4>
    <input type="text" name="email" v-model="email">
    <input type="password" name="password" v-model="password">
    <select name="age" id="age">
      <option v-for="(data, index) in age" :key="index" value="">{{data}}</option>
    </select>
  </div>
  </div>
</template>

<script>
import Navbar from '../components/module/Navbar'
export default {
  name: 'Home',
  components: {
    Navbar
  },
  data: function () {
    return {
      count: 1,
      firstName: 'Hanif',
      lastName: 'Kumara',
      email: '',
      password: '',
      profiles: [
        { id: '1', name: 'Hanif Kumara', score: 90, hobby: 'Game', address: 'Sukoharjo, Jawa Tengah' },
        { id: '2', name: 'Nanda Febriansah', score: 85, hobby: 'Anime', address: 'Bekonang, Jawa Tengah' },
        { id: '3', name: 'Fathoni Novantoro', score: 75, hobby: 'Martial Arts', address: 'Klaten, Jawa Tengah' },
        { id: '4', name: 'Kurniawan Khoiruddin', score: 80, hobby: 'Farmer', address: 'Ngemul, Sukoharjo, Jawa Tengah' },
        { id: '5', name: 'Allam Qobus AF', score: 85, hobby: 'Football', address: 'Sukoharjo, Jawa Tengah' },
        { id: '6', name: 'Farhan Meyega Umar', score: 80, hobby: 'Football', address: 'Sidoarjo, Jawa Timur' },
        { id: '7', name: 'Satria Ardiansah', score: 75, hobby: 'Playing PUBG', address: 'Weru, Jawa Tengah' },
        { id: '8', name: 'Ilyasa Roshid Zufar', score: 80, hobby: 'Sleep', address: 'Klaten, Jawa Tengah' }
      ]
    }
  },
  methods: {
    addCount: function () {
      this.count += 1
    },
    minCount: function () {
      this.count -= 1
    }
  },
  computed: {
    filterScore: function () {
      const filterResult = this.profiles.filter(res => res.score >= 85)
      return filterResult
    }
  }
}
</script>
