<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Albert" :iniProps="tes+'tes'"/>
    <input v-model="tes">
    {{ peringatanForm }} <br>
    <button v-if="tes !== ''">
        INI BUTTON
    </button>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'NewView',
  data(){
      return{
        tes: "Ini Tes 123",
        peringatanForm: "",
      }
  },
  components: {
    HelloWorld
  },
  methods:{
      cobaTes(){
          console.log("coba tes ketrigger");
      },
  },
  watch:{
      tes(){
          this.cobaTes();

          if(this.tes == ''){
              this.peringatanForm = "Tes tidak boleh kosong!";
          }
          else{
              this.peringatanForm = "";
          }
      },
  },

}
</script>
