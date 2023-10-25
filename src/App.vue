<script>
export default{
  data(){
    return{
      url:""
    }
  },
  methods:{
    showImg(event){
      var id = event.target.id;
      if(id == 'da-vinci'){
        this.url="./src/assets/mona-lisa.jpg"
      }else if(id == 'gustav'){
        this.url="./src/assets/gustav.jpg"
      }else{
        this.url="./src/assets/dante.jpg"
      }
    },
    deAcive(){
      this.url=''
    }
  }
}
</script>

<template>
  <div class="text">
    <h1>Картинная галерея – великие художники</h1>
  </div>
  <div class="wrapper-content">
    <div class="card">
      <div class="card-img-wrapper da-vinci" @click="showImg" id="da-vinci">
      </div>
      <p>Lionardo da Vinci</p>
    </div>
    <div class="card">
      <div class="card-img-wrapper gustave" @click="showImg" id="gustav">
      </div>
      <p>Gustave Caillebotte</p>
    </div>
     <div class="card">
      <div class="card-img-wrapper gabriel" @click="showImg" id="dante">
      </div>
      <p>Dante Gabriel Rossetti</p>
    </div>
  </div>
  <div class="galerey-active" id="active" v-show="url != ''" @click="deAcive">
    <img :src="url" alt="">

  </div>
</template>

<style scoped>
  .text{
  color: #b5cef5;
  } 
  .galerey-active{
    background-color: #312c4da7;
    position: absolute;
    right: 0;
    top: 0;
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .wrapper-content{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    border-radius: 20px;
    width: 1080px;
    padding: 20px;
    min-height: 600px;
    margin-top: 20px;
    background-color: #312c4d;
  }
  .card {
    margin: 20px;
    display: flex;
    flex-wrap: wrap;
    text-align: center;
    justify-content: center;
    width: 400px;
    height: 300px;
    background-color: #53699e;
    transition: 0.5s ease;
  }
  .card:hover .card-img-wrapper{
    transform: scale(1.2);
  }
  .card-img-wrapper{
    width: 400px;
    height: 250px;
    background-size: cover;
    background-position-y: -100px;
    transition: 0.5s ease;
  }
  .da-vinci{
    background-image: url("./src/assets/mona-lisa.jpg");
    
  }
  .gustave{
    background-image: url("./src/assets/gustav.jpg");
    background-position-y: -30px;
  }
  .gabriel{
    background-image: url("./src/assets/dante.jpg");
  }
  .img-active{
    width: 800px;
    height: 500px;
  }
</style>
