<template> 

 <div>
  <div class="hidden-sm-and-up" >
     <v-navigation-drawer
     v-model="drawer"
     absolute
     app
     temporary
     height="800"
     >
     <v-list>
         <v-list-item>
            <v-list-item-content class=" mt-2 ml-13">
                <v-list-item-title class="title">FEIJONES
                    <v-btn style="z-index:100;" class="ml-8" text color="rgba(90,13,4,255)" small fab @click="drawer = false"> <v-icon> mdi-arrow-left</v-icon> </v-btn>
                 </v-list-item-title> 
                <v-list-item-subtitle class="subTitle">Feijao e Feijoada</v-list-item-subtitle>
            </v-list-item-content>

         </v-list-item>
     </v-list>

  

         <!-- colocar link do componente em 'link' -->
        <v-list dense
         v-for="([color,icon,text,click],i) in items"
         :key="i"
        >
          <v-divider class="mb-5"></v-divider>
        <v-list-item
            link
        >
          <v-list-item-icon class="justify-start">
                <v-icon  size="30" :color=color> {{icon}} </v-icon> 
          </v-list-item-icon> 

          <v-list-item-content @click="$vuetify.goTo(click); drawer=!drawer" >
             <v-list-item-title>{{text}}</v-list-item-title>
          </v-list-item-content>

         </v-list-item>
        </v-list>
          <v-divider/>
        <img class="mt-16 ml-7" src="@/assets/drawerLogo.png" alt="a">
     </v-navigation-drawer>
  </div>

 <v-app-bar
     app
     dark
     :height=barSize
     flat
    absolute
    color="black"
    class="appBar2"
     >
<v-col>
    <v-row justify="center">
    <img :class=imgStyle :src=imgSize style="z-index:10;">
    </v-row>
 

  <v-row justify="space-between">
   <v-btn style="z-index:100;" class="btnMenu hidden-sm-and-up" color="rgba(90,13,4,255)" fab>
     <v-app-bar-nav-icon
     @click.stop="drawer = !drawer"
     >
     </v-app-bar-nav-icon>
     </v-btn>
       <v-btn style="z-index:200;" class="btnCart hidden-sm-and-up" color="rgba(90,13,4,255)" fab >
      <v-icon>mdi-cart</v-icon>
     </v-btn>
   </v-row>

   <v-spacer/>

    <v-app-bar
    class="appBar2 expand" 
    color="rgba(90,13,4,0.7) "
    :width= imgWi
    :height= imgHe
    flat
    >
   
    <v-row  justify="end" class="mt-9 hidden-md-and-down">
         <v-btn  style="position:relative;z-index:100;"  x-large text class="mr-3 ml-5" >
          <span  class="appBar4 " >Home</span>
        </v-btn>
        <v-btn @click="$vuetify.goTo('#historia'); " x-large text class="mr-3">
          <span class="appBar4">Feijões</span>
        </v-btn>
        <v-btn @click="$vuetify.goTo('#form')" x-large class="mr-3"   text >
          <span class="appBar4">Fale Conosco</span>
        </v-btn>
    </v-row>
    </v-app-bar>

 
 </v-col>
 </v-app-bar>

 <v-app-bar
 
    inverted-scroll
    app
    class="appBar2 expand  " 
    color="rgba(90,13,4,0.9) "
    :width= imgWi
    :height= imgHe
    flat
    >



    <v-row justify="start">
     <img v-if=!isMobile   height="100" src="@/assets/logoFooterMob.png" > 
    </v-row>

    <v-row class="mb-2" align="end" v-if="!isMobile" justify="space-between" >
        <v-row justify="end">
         <v-btn style="position:relative;z-index:100;" @click="$vuetify.goTo('#hero')"  x-large text class="mr-16" >
          <span  class="appBar4  ">Home</span>
        </v-btn>
        <v-btn  @click="$vuetify.goTo('#historia')" x-large text class="mr-16">
          <span  class="appBar4">Feijões</span>
        </v-btn>
        <v-btn  @click="$vuetify.goTo('#form')"  x-large class="mr-16" rounded outlined text >
          <span class="appBar4">Fale Conosco</span>
        </v-btn>
        </v-row>
        
         
    </v-row>
   <v-col class="mt-1" cols="12" v-else>
    <v-row  justify="space-between"  >
      <v-btn  class="" color="rgba(90,13,4,255)"  dark fab>
            <v-app-bar-nav-icon @click.stop="toTop()">
            </v-app-bar-nav-icon>
     </v-btn >
     <img  height="75" src="@/assets/logoFooterMob.png" > 
       <v-btn class="mr-2" color="rgba(90,13,4,255)" dark fab >
      <v-icon>mdi-cart</v-icon>
     </v-btn>
    </v-row>
   </v-col>
    </v-app-bar>
 </div>

</template>

<script>

export default {
    name: 'Navigation',
    data:() =>({
        drawer:false,
        img:   [
            { 
              src: require ('@/assets/bkMobile.png'),
              width:"",
              hight:"88"
              
            },
            { src: require ('@/assets/bkDesktop.png'),
              width:"22200",
              hight:"95"
            }
            
            ],
        items:[
            ["orange","mdi-home-outline","Home", "#hero"],
            ["orange","mdi-silverware-variant","Feijões","#historia"],
            ["orange","mdi-message","Fale conosco","#form"],
            ["orange","mdi-cart","Carrinho","#hero"]



            
        ]
    }),

    methods: {
        toTop (){
            this.$vuetify.goTo(0)
            this.drawer = true
        }
    },
    computed:{
        isMobile() {
            switch (this.$vuetify.breakpoint.name) {
                case "xs":
                    return true;
                case "sm":
                    return true;
                default: 
                    return false;
            }
      },
      
        imgSize(){
            switch(this.$vuetify.breakpoint.name){

                case"xs":
                    return this.img[0].src
            default: return this.img[1].src
            }
            
        } ,

        imgWi(){
             switch(this.$vuetify.breakpoint.name){

                case"xs":
                    return this.img[0].width
            default: return this.img[1].width
            }

        },
        imgHe(){
             switch(this.$vuetify.breakpoint.name){

                case"xs":
                    return this.img[0].hight
            default: return this.img[1].hight
            }


        },

        barSize(){
            switch (this.$vuetify.breakpoint.name){
                case"xs":
                    return 186
                default: return 270
            }
        },
        imgStyle(){
            switch (this.$vuetify.breakpoint.name){
                case"xs":
                    return "appBar2"
                default: return ""
            }
            
        },

        
        

    },
    
    
  }
</script>

<style scoped>
.title{
    color:#211004 !important;
    font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
}
.subTitle{
    color: #8a542e !important;
    font-family: bold;
}
.appBar3{
   padding-top:4rem ;
   font-size: 20px;

}
.appBar4{
    font-size:22px;
    color: white;
}
.spaceBar{
    width:850px ;
}


.btnMenu{
   
    margin-bottom:7.4rem;
}
.btnCart{
  
    margin-bottom:7.4rem ;
}
.backDesktop{
    align-content: center;
}


.appBar2{
    position: absolute;
    bottom: 0px;
   
    
}




</style>