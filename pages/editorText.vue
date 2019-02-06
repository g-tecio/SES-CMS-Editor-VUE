<template>
  <div id="app">
    <!-- <AppToolbar/> -->
    <vue-editor v-model="content"></vue-editor>
    <button class="btn" type="button" v-on:click="postNote()">
      <span>Subir Nota</span>
    </button>
  </div>
</template>
<style>
  .btn {
  position: relative;

  display: block;
  margin: 30px auto;
  padding: 0;

  overflow: hidden;

  border-width: 0;
  outline: none;
  border-radius: 2px;
  box-shadow: 0 1px 4px rgba(0, 0, 0, .6);

  background-color: #303ba5;
  color: #ecf0f1;

  transition: background-color .3s;
  }

  .btn:hover, .btn:focus {
  background-color: #27ae60;
  }

  .btn > * {
  position: relative;
  }

  .btn span {
  display: block;
  padding: 12px 24px;
  }

  .btn:before {
  content: "";

  position: absolute;
  top: 50%;
  left: 50%;

  display: block;
  width: 0;
  padding-top: 0;
    
  border-radius: 100%;

  background-color: rgba(236, 240, 241, .3);

  -webkit-transform: translate(-50%, -50%);
  -moz-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  -o-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  }

  .btn:active:before {
  width: 120%;
  padding-top: 120%;

  transition: width .2s ease-out, padding-top .2s ease-out;
  }

  /* Styles, not important */
  *, *:before, *:after {
  box-sizing: border-box;
  }



  
</style>

<script>

  import AppToolbar from '../components/AppToolbar.vue'
   import { VueEditor } from 'vue2-editor'
 
   export default {
 
   components: {
      VueEditor,
      AppToolbar
   },
 
   data() {
       return {
        content: '<h1>Ingresa tu nota </h1>' ,
        postData:{}
       }
    }, 
    methods: {

      postNote(){
        let note = String(this.content);
        this.postData= {
          id:"id generico",
          article:note,
          author:"Autor generico",
          location: "Locacion generica",
          date: "crear metodo para el date",
          type: "tipo generico",
          status: "status generico",
          editor_id: "id generico"
        }
        console.log(this.postData);
      } 
    }
   }

   
 </script> 
