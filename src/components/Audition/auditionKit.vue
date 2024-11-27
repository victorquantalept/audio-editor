<template>
    <v-container class="container-format" elevation="5">
    <v-card class="pa-4">
      <div>
        <h3 class="text-center " style=" font-size: 20px;">Metadata Editor</h3>
        <v-divider :thickness="3" color="black my-1"></v-divider>
      </div>
      <div class="mt-5">
        <!-- <v-select label="Select Item" return-object variant="plain"
            density="compact"
            class="align-center justify-center mt-5"
            style="border-radius: 10px; height: 50px; background-color: #e6e6ff;">
        </v-select> -->
      <audioTextField label="Title" v-model="audioForm.Title" />
      <audioTextField label="Singers" v-model="audioForm.Singers" />
      <audioTextField label="Composer" v-model="audioForm.Composer" />
      <audioTextField label="Album" v-model="audioForm.Album" />
      <!-- <audioTextField label="GenereS" v-model="audioForm.Genere" /> -->
      <v-select label="Genere" return-object variant="plain"
            density="compact"
            class="align-center justify-center mt-3"
            style="border-radius: 10px; height: 45px; background-color: #e6e6ff;">
        </v-select>
      <!-- <audioTextField label="VibeS" v-model="audioForm.Vibe" /> -->
      <v-select label="Vibe" return-object variant="plain"
            density="compact"
            class="align-center justify-center mt-3"
            style="border-radius: 10px; height: 45px; background-color: #e6e6ff;">
        </v-select>
      <audioTextField label="Lyricist" v-model="audioForm.Lyricist" />
      <!-- <audioTextField label="Sample RateS" v-model="audioForm.SampleRate" /> -->
      <v-select label="Sample Rate" return-object variant="plain"
            density="compact"
            class="align-center justify-center mt-3"
            style="border-radius: 10px; height: 45px; background-color: #e6e6ff;">
        </v-select>
      <!-- <audioTextField label="CodecS" v-model="audioForm.Codec" /> -->
      <v-select label="Codec" return-object variant="plain"
            density="compact"
            class="align-center justify-center mt-3"
            style="border-radius: 10px; height: 45px; background-color: #e6e6ff;">
        </v-select>
      <audioTextField label="Year" v-model="audioForm.Year" />
      <!-- <v-sheet class="d-flex mx-auto align-center justify-center mb-3 mt-3 text-center pa-6" width="450" height="450"
        color="#e6e6ff" elevation="0" style="border-radius: 16px;"> -->
        <!-- <div class="text-center" >
          <v-row class="mt-5">
            <v-col class="box1">Thumb Nail</v-col>
            <v-col class="box2"><v-card><v-img max-width="200" max-height="200" />Image Here</v-card></v-col>
            <v-col class="box3"><v-row><v-btn>Choose from Gallery</v-btn></v-row><v-row><v-btn>Delete</v-btn></v-row></v-col>
          </v-row>         
        </div>         -->
        <div class="image-box">
          <div class="box1">Thumb Nail</div>
          <div class="box2"><v-card></v-card>Image</div>
          <div class="box3">
            <v-btn class="mb-1 "  color="primary">Gallery</v-btn>
            <v-btn color="primary">Delete</v-btn>
          </div>
        </div>
      <!-- </v-sheet> -->
      <v-row justify="space-between" class="mt-8 ml-3 mr-3 mb-3">
         <v-btn color="primary" outlined >
           Reset
         </v-btn>
         <v-btn color="primary" >
            <v-icon left>mdi-content-save</v-icon>
            Save
         </v-btn>
      </v-row>
    </div>
   
    </v-card>
</v-container>
</template>

<script lang="ts">
import { defineComponent, ref,  } from 'vue';
// import axios from 'axios';
import audioTextField from './audioField.vue';
// import { useRouter } from 'vue-router';

export default defineComponent({
  name: 'MedataEditor',
  components: {
    audioTextField,
  },
  setup() {
    const audioForm = ref({
      Title: '',
      Singers: '',
      Composer: '',
      Album: '',
      Genere: '',
      Vibe: '',
      Lyricist: '',
      SampleRate: '',
      Codec: '',
      Year: '',
    
    });
    return {
      audioForm,
    };
  }
});
</script>
<style scoped>
  .container-format{    
    background-color: rgb(241, 252, 248);
    width: 100%;
    height: 100%;
    
  }
  .image-box {
    margin-top: 15px;
    border: 1px solid black;
    border-radius: 5px;
    display: flex;
    flex-direction: row;
    padding: 8px;
    justify-content: space-around; 
    align-items: center;
  }
  .box1 {      
      border-color: solid 5px red;
      border-radius: 2px;
      background-color: rgb(199, 226, 226);
      align-content: center;
      height: 40px;
      margin-left: 10px;
      text-align: center;
  }
  .box2 {
    margin-top: 0px;
    border-radius: 10px;
    border-color: solid 5px rgb(211, 25, 25);
    background-color: rgb(201, 177, 177);
    width: 150px;
    height: 100px;
    /* align-items: center; */
    /* justify-content: space-around;  */
    margin-left: 25px;
    
    text-align: center; 

  }
  .box3 {
    align-items: center;
    justify-content: center; 
    text-align: center; 
    
  }
</style>