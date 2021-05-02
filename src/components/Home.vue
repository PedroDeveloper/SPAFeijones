<template>
 
    <section id="hero">
     <v-container>
        <v-row
          align="center" :justify="justifyContent"
        >
          <v-col cols="11" xs="11" sm="11" md="10">
            <v-row align="center" justify="center" justify-xl="end" justify-sm="center" justify-xs="center" justify-md="center" >
              <v-col cols="12" md="6" xl="8" sm="6">
               <h1 class="font-weight-bold mb-4 black--text"
                :style="{'font-size': fontSize }"
               >
                  O Brasileiro <br />Ama feijão!
               </h1>
               <h2 class="font-weight-light black--text custon-selector">
                 E agora chegou um jeito<br />fácil de consumir!
               </h2>

                <v-btn color="black" dark 
                  class="mt-4" x-large 
                   @click="getLinkWhastapp()"
                >
                   (71) 9 9999-2891

                </v-btn>
                <v-btn rounded fab 
                  class="mdi-wpp" color="green" dark
                  height="50"
                  @click="getLinkWhastapp()"
                >
                    <v-icon>mdi-whatsapp</v-icon>
                </v-btn>
              
              </v-col>
            </v-row>
          </v-col>
        </v-row>
        </v-container>
  </section>

  
</template>

<script>

  export default {
    name: 'Home',

    computed: {
      fontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          console.log("xs")
          return "3.2rem";
        case "sm":
           console.log("sm")
          return "3rem";
        case "md":
           console.log("md")
          return "4rem";
        case "lg":
           console.log("lg")
          return "4rem";
        case "xl":
          console.log("xl")
          return "6rem";
        default: return "3rem";
      }
    },
     justifyContent() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return "end";
        case "sm":
          return "end";
        case "md":
          return "center";
        case "lg":
          return "center";
        case "xl":
          return "center";
        default: return "center";
      }
    },

    isMobile() {
      switch(this.$vuetify.breakpoint.name) {
        case "xs":
          return true
        case "sm":
            return true
        default: 
          return false
      }
    }

  },
    methods: {
       getLinkWhastapp() {
        var url = `https://api.whatsapp.com/send?phone=${5571999992891}&text=Olá, gostaria de ver o cardapio!`
        window.open(url, '_blank')
      }
    }
    
  }
</script>

<style scoped>

  #hero {
    background: url("../assets/bg.jpeg");

    display: flex;
    align-items: center;
    justify-content: center;
    padding-top: 14rem;
  }
  .mdi-wpp {
    position:relative;
    top: 44px;
    right: 60px;
    z-index: 1;
  }

  h1 {
    font-size: 3.0rem;
  }

  h2 {
    font-size: 1.5rem !important;
  }

 @media only screen and (min-width: 760px) {
  #hero {

    padding: 17rem 0;
  }
}
</style>


