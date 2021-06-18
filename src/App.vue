<template>
  <Title title="Catatan Pengeluaran"/>
  <FormMahasiswa @entri-mahasiswa = "entriMahasiswa($event)"/>
  <ListMahasiswa v-if="dataMahasiswa.length>0" :dataMahasiswalist="dataMahasiswa"/>
</template>

<script>
import Title from './components/Title.vue'
import ListMahasiswa from './components/ListMahasiswa.vue'
import FormMahasiswa from './components/FormMahasiswa.vue'
export default {
  name: 'App',
  components: {
    Title,
    ListMahasiswa,
    FormMahasiswa,
  },
  data(){
    return{
      dataMahasiswa : [
        {nim: 'D111811072', nama: 'Gilang Prasetya', kelas: 'IF-6B'},
        {nim: 'D111811071', nama: 'Gogol Prasetya', kelas: 'IF-6B'},
        {nim: 'D111811073', nama: 'Gilang Gogol Prasetya', kelas: 'IF-6B'}
      ],
    }
  },
  methods:{
    entriMahasiswa(event){
      this.dataMahasiswa.push(event);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>