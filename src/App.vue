<template>
  <Header></Header>
  <main>
    <Refresh @refresh="refreshFacts"></Refresh>
    <Facts :facts="facts"></Facts>
  </main>
</template>

<script>
  import Header from './components/Header.vue';
  import Facts from './components/Facts.vue';
  import Refresh from './components/Refresh.vue';
  

  export default {
    name: 'App',
    components: {
    Header,
    Facts,
    Refresh,
    },

    data(){
      return{
        facts:[]
      }
    },

    async created () {
      
      this.facts =await this.get();
      
    },

    methods:{

    async refreshFacts(){
      console.log("clicked");
      this.facts =await this.get();
    },

    async get(){
      const nr = Math.floor(Math.random()*33)+1;


      const res = await fetch(`https://catfact.ninja/facts?page=${nr}`);
      const data = await res.json();
      return data.data;
    }

    }



  }
</script>

<style scoped>

</style>
