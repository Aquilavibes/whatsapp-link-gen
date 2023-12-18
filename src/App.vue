<template>


  <div class='container'>
  <h1> Whatsapp Link Generator</h1>
  <input type='tel' placeholder="Phone Number with country code  " id='numb' v-model='no'><br><br>
  <input type='text' placeholder="Message(optional)" id='text' v-model='text'><br><br>
  <button type='submit' @click='concat' id='gene'>Generate Link</button><br><br>
 <br> <hr>
  <input type='clipboard' id='linky' placeholder='link will generate here' v-model='added'><br><br>
 
  <button id="copy" @click="clipy">{{ currentvalue }}</button>
  <br><br>

  <footer>Website developed by Cyber-quils</footer>

</div>

</template> 

<script>
import main from './assets/main.css'

export default {

  data(){
    return {
      htt: 'https://wa.me/',
      write: '/?text=',
      no: '',
      text: '',
      added: '',
      currentvalue: 'Copy link',
      changedvalue: 'Copy Link'
      
    }
    }
  ,

  methods: {
  concat() {
this.added = this.htt + this.no + this.write + encodeURIComponent(this.text)
console.log(this.htt + this.no + this.write + encodeURIComponent(this.text))

    },

   
      


    clipy(){
      const el = document.createElement('textarea');
      el.value = this.added;
      document.body.appendChild(el);
      el.select();
      document.execCommand('copy');
      document.body.removeChild(el);
      this.currentvalue = 'copied!';
      setTimeout(() => {
        this.currentvalue = this.changedvalue;
      
      },3000)
     
    }
  }
  }
</script>

<style scoped>

input {
   border-bottom: solid black;
  border-top: white;
   border-left: white;
    border-right: white;
    width: 10px;
}


footer {
  text-align: center;
  font-size: 12px;
}

h1 {
  margin-left: 150px;
  color: blue;
}

#copy {
  width: 150px;
  height: 30px;
  margin-left: 150px;
  background-color: blue;
  color: white;
}

#linky {
  width:300px;
  height: 40px;
  font-size: 20px;
  margin-left: 150px;
  background-color: rgba(228, 221, 221, 0.966)255, 255, 255, 0.966;
}


p {
  background-color: white;
 
}

.container {
  background-color: rgb(255, 255, 255);
  width: 600px;
  height: 480px;
  margin-left: 330px;
  
}

#text {
  width: 500px;
  height: 100px;
  font-size: 15px;
  margin-left: 60px;
}

#numb {
  width: 500px;
  height: 40px;
  font-size: 20px;
  margin-left: 60px;
}

#gene {
  width: 180px;
  height: 50px;
  color: white;
  background-color: blue;
  border-radius: 20px;
  margin-left: 200px;
}

@media (max-width: 1000px) {
  .container {
    margin-left: 2px;
    width: 355px;
    background-color: white;
    height: 680px;
   

  }

  h1 {
  font-size: 30px;
  color: blue;
margin-left: 10px;
  
   
}

#text {
  width: 320px;
  height: 150px;
  font-size: 20px;
  margin-left: 20px;
  
 
}

#numb {
  width: 300px;
  height: 100px;
  font-size: 19px;
  margin-left: 30px;
   margin-top: 50px;
   
}


#gene {
  width: 200px;
  height: 50px;
  color: white;
  background-color: blue;
  border-radius: 20px;
  margin-left: 80px;
}

#copy {
  width: 150px;
  height: 30px;
  margin-left: 20px;
  background-color: blue;
  color: white;
}

#linky {
  width:300px;
  height: 40px;
  font-size: 20px;
  margin-left: 20px;
  background-color: rgba(228, 221, 221, 0.966)255, 255, 255, 0.966;
  margin-top: 20px;
}


input {
   border-bottom: solid black;
  border-top: white;
   border-left: white;
    border-right: white;
    width: 10px;
}

hr {
  width: 300px;
  
}



}

</style>



