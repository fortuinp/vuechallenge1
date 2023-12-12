<template>
  <div class="row" >
   
    <div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
    All Products
  </button>
  <ul class="dropdown-menu" >
    <li v-for="i in Smoothies" :key="i.id" >
      <a class="dropdown-item" @click="displayproduct" href="#" >{{i.flavour}}</a>
    </li>

  </ul>
    </div>
 <div>
    <input type="text" @input="search">
 </div>
    </div>
   

  <div class="wrapper">
  <div class="row" v-if="Smoothies.length">
    <div class="prodCard" v-for="smoothie in Smoothies" :key="smoothie.id"> 
      <div class="card-header">
        <h3>{{ smoothie.flavour }}</h3>
      </div>
      <div class="card-body">
        <img :src="smoothie.url" :alt="smoothie.flavour" loading="lazy">
        <h4>{{ smoothie.price }}</h4>
      </div>
    </div>
  </div>
</div>

</template>

<script>


export default {
  name: 'App',
  data(){
  return {
    Smoothies:[
   { id: 1,
          flavour: "strawberry",
          price: 50,
          url: "https://i.postimg.cc/zDFn0N5Q/240-F-59738474-5-NTSry-Zt-Ri-Zejj4d-Upj-Qhssiga-Erqinl.jpg",
        },
        {
          id: 2,
          flavour: "choc chip",
          price: 61,
          url: "https://i.postimg.cc/pLfxnsKK/240-F-60195257-Yb0t1-Gl-L6-Yhb-C0c0bp-Nt06-To-SMAsdg82.jpg",
        },
        {
          id: 3,
          flavour: "banana",
          price: 48,
          url: "https://i.postimg.cc/P55JTGgP/240-F-60195267-o-Usx-A2-V7-UIwng-JNOi2ss-MOSEu-Oj-LMRC1.jpg",
        },
        {
          id: 4,
          flavour: "kiwi",
          price: 25,
          url: "https://i.postimg.cc/bJcqG4B0/240-F-62583240-YUkve-XVAOZC9-Kupg0r-MRXl-C3-S6-AJ2sa-R.jpg",
        },
        {
          id: 5,
          flavour: "orange",
          price: 97,
          url: "https://i.postimg.cc/W1xvKQTR/240-F-63337375-f-KOc-YM95-ZH2-HGld-Jc7nv-Oquxuv5x-TPiz.jpg",
        },
    ],
  }
  },
  components:{},
  methods:{
    displayproduct(){
       let wrappper=document.getElementsByClassName('wrapper')
       wrappper.textContent=''

  },
  search(){
    
  }
  },
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
.wrapper :is(.row) {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
.prodCard {
  width: 15rem;
  height: 13rem;
}
.prodCard :is(>*, img){
  width: 100%;
  aspect-ratio: 1/1;
}
</style>
