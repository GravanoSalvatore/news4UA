<template>
  <div>
    <v-card absolute app color="primary" dark flat>
      <v-container>
        <v-row align="start">
          <v-col cols="12" md="3">
            <h4 class="text-h5 font-weight-bold">
              Good News
            </h4>
            <p class="text-body-1">
              Good News are your trusted source for up-to-the-minute news covering the world of cryptocurrencies and the dynamic realm of business. Our mission is to provide our readers with the freshest and most reliable information needed to make informed decisions in the fields of investment, finance, and technology.
            </p>
          </v-col>

          <v-col cols="12" md="3">
            <v-list color="transparent" flat>
              <v-subheader class="text-h6">HOME</v-subheader>
              <v-list-item-group color="primary">
                <v-list-item
                    
                    
                    dense
                    
                >
                  <v-list-item-content>
                    <v-list-item-title
                        class="text-body-1"
                       
                    >
                  <ul>
                    <div class="li">ARTICLES</div>
                    <div class="li">NEWS</div>
                    <div class="li">CRYPTO</div>
                    <div class="li">BUSINESS</div>
                    <div class="li">TECHNOLOGY</div>
                    <div class="li">ENTERTAINMENT</div>
                    <div class="li">HEALTH</div>
                    <div class="li">SCIENCE</div>
                    <div class="li">SPORT</div>
                  </ul>
                  
                  
                  </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-col>

          <v-col cols="12" md="3">
            <v-list color="transparent" flat>
              <v-subheader class="text-h6">ABOUT</v-subheader>
              <v-list-item-group color="primary">
                <v-list-item
                   
                   
                   
                >
                  <v-list-item-content>
                    <v-list-item-title
                        class="text-body-1"
                       
                    >
                    <ul>

                      <div class="li">FOREX</div>
                    <div class="li">TOP</div>
                    <div class="li">NFT</div>
                    <div class="li">DEFI</div>
                    <div class="li">CONTACT</div>
                    <div class="li">LOGIN</div>
                   <div class="li">VIDEO</div>
                    <div class="li">DONATE</div>
                  </ul>
                  </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-col>

          <v-col cols="12" md="3">
            <div>
              <h5 class="text-h6 font-weight-bold">
                Subscribe
              </h5>
              <p class="text-body-1">
                
              </p>
            </div>

            <v-row>


              <div class="wrap">
<div class="div "> 
    <button @click="searchClose" class="close">
        <img style="width:45px;color:black" 
        src="https://freesvg.org/img/close-button.png">
    </button> 
  
  <div v-for="item in news"
  
  :key="item">
  

  <!-- <img class="img-fluid w-100" v-if="item.urlToImage" :src="item.urlToImage" style="object-fit: cover;">
 <img class="img-fluid w-100" v-else src="#" style="object-fit: cover;">
                                -->
 <a class="title" :href="item.url" 
         target="_blank ">
         {{item.title}}</a><br/><hr/>
      
  
  </div> 
  </div>
</div>





              <v-col cols="8">
                <v-text-field
                id="input"
                v-model="searchT" 
                    placeholder="Search news" 
                    v-on:input="onSearchType"  
                    class="form-control mt-1  bg-black"  
                    aria-label="Search"
                    type="text"
                ></v-text-field>
                <!-- <v-input
                   



                    v-model="searchT" 
                    placeholder="Search news" 
                    v-on:input="onSearchType"  
                    class="form-control mt-1 input bg-black"  
                    aria-label="Search"
                    type="text">
                </v-input> -->
              </v-col>

              <v-col cols="4">
               
               
              </v-col>
            </v-row>
          </v-col>
        </v-row>
        <br/><br/>
        <div style="padding:10px">
          <v-avatar class="elevation-4" color="">
                  <v-icon large>mdi mdi-twitter</v-icon>
                </v-avatar>
        <v-avatar class="elevation-4" color="">
                  <v-icon large>mdi mdi-instagram</v-icon>
                </v-avatar>
                <v-avatar class="elevation-4" color="">
                  <v-icon large>mdi mdi-whatsapp</v-icon>
                </v-avatar>
                <v-avatar class="elevation-4" color="">
                  <v-icon large>mdi mdi-linkedin</v-icon>
                </v-avatar>
                <v-avatar class="elevation-4" color="">
                  <v-icon large>mdi mdi-youtube</v-icon>
                </v-avatar>
              </div>
             
        <div class="text-center mt-6">
          Copyright &copy;
          <a
              class="white--text"
             
              rel="noopener noreferrer"
             
          >GOOD NEWS</a
          >
         
          {{ new Date().getFullYear() }}. All rights reserved.
        </div>
        <br/><br/><br/><br/>
        <back/>
      </v-container>
    </v-card>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  methods:{
    onSearchType: function () {
      const search = (document.querySelector(".div").style.display = "block");
      var url =
        "https://api-epicnews404.azurewebsites.net/Articles/TopHeadlines?SiteId=1&CategoryId=3&Language=14&Page=2&PageSize=100" +
        "&q=" +
        this.searchT;

      axios
        .get(url)
        .then((response) => {
          this.news = response.data.items;
        })
        .catch((error) => {
          console.log(error);
        });
    },
    searchClose() {
      const searchClosed = (document.querySelector(".div").style.display =
        "none");
        const searchClosed2 = document.getElementById("input").value ='';
       
    },
  },
  components:{
    back:()=>import ('../../components/fishki/back-to-top.vue')

  },
  data: () => ({
    news: [],
      searchT: "",
      news: [],
    heroui: [
      {
        text: "Github",
        href: "https://github.com/AGDholo",
      },
      {
        text: "Themes",
        href: "https://heroui.net/",
      },
    ],
    shock: [
      {
        text: "Download",
        href: "https://github.com/AGDholo/giraffe",
      },
      {
        text: "Issues",
        href: "https://github.com/AGDholo/giraffe/issues",
      },
      {
        text: "LICENSE",
        href: "https://github.com/AGDholo/giraffe/blob/master/LICENSE",
      },
    ],
  }),
};
</script>
<style scoped lang="scss">
.close{
//  position: ;
  // left:228px;
// bottom:600px;
//   left:170px;
 }
.div {
   box-shadow: 0 0 20px 0 rgb(0 0 0 / 50%);
  position: fixed;
  border: 2px solid white;
  display: none;
  width: 250px;
  margin-left: px;
  margin-right: 30px;

  border-radius: 5px;

  top: 67px;
  padding: 20px;

  height: 515px;
  overflow-x: hidden;
  overflow-y: auto;
   background-color: white;
  color: rgb(3, 3, 3);
  z-index: 5000;
  //   display: none;
  @media screen and (max-width: 767px) {
  }
}
.elevation-4{
  margin: 7px;
}
</style>
