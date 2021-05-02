<template>
<!-- <v-app> -->
    <v-footer color="rgba(90,13,4,255)"  >
        <v-col cols="12 mt-2" v-show="isMobile">
            <v-row justify="center">
                <h2 class="h3 white--text">Fale Conosco</h2>
            </v-row>
        </v-col>
        <!-- LINHA PARA A LOGO 
        <v-row style="border: 1px solid orange">
            <v-img  height="120" src="@/assets/logo2.png" alt="a"></v-img>
        </v-row> -->
        <v-row justify="space-around" justify-md="center" 
            align="center">
            <span  v-if="!isMobile" class="white--text mr-2 mt-7 ">@FEIJONES</span>
            <div v-for="(icon,i) in icons" :key="i"
                icon
            >
                <v-col   cols="12" md="2" xl="12">
                      <v-row >
                        <v-btn  class=" mt-6 mr-3"  :color=icon.btnColor 
                            fab :small=!isMobile
                            @click="icon.cta"
                        >
                            <v-icon  :color=icon.color>{{icon.icon}}</v-icon>
                        </v-btn>
                    </v-row>
                </v-col>
          </div>
        </v-row>
        <v-col cols="12"  >
            <v-row justify="center" v-if=isMobile>
              
            </v-row>
            <v-row justify="center" v-else>
          
            </v-row>
            
        </v-col>
        <v-col  class="mt-4" cols="12">
            <v-row justify="center" justify-md="center" justify-lg="center">
                <span class="  h2" >Endereço: Av. Urbana, Ponto certo</span>
            </v-row>
        </v-col>
         
    </v-footer>
<!-- </v-app> -->
</template>
<script>

export default {
  
   name:'Footer',
    data:()=>({
        icons:[
                {
                    icon:"mdi-instagram", color:"white",btnColor:"red", cta: () => {
                        alert("Em breve...")
                    }
                },
                { 
                    icon:"mdi-whatsapp", color:"white", btnColor:"green", cta: () => {
                        var url = `https://api.whatsapp.com/send?phone=${5571999992891}&text=Olá, gostaria de ver o cardapio!`
                        window.open(url, '_blank')
                    }
                },
                {
                    icon:"mdi-facebook", color:"white",btnColor:"blue", cta: () => {
                         alert("Em breve...")
                    }
                },
                {
                    icon:"mdi-twitter", color:"white",btnColor:"blue", cta: () => {
                         alert("Em breve...")
                    }
                }
             ]
    }),
    computed: {
        isMobile () {
            switch(this.$vuetify.breakpoint.name) {
                case 'xs':
                    return true
                case 'sm':
                    return true
                default: 
                    return false
            }
        }
    }
}
</script>
<style scoped>
.h2{
    color: white;
    font-size:100% ;
}
.h3{
    font-size: 120%;
}
    
</style>