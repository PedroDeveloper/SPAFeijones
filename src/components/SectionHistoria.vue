<template>
    
        <section id="historia">
           <v-container id="teste">
               <v-row v-if="isMobile">
                   <v-carousel cycle height="300px" class="mt-16 pt-15"
                        hide-delimiter-background hide-delimiters
                        :show-arrows="false"
                    >
                    <v-carousel-item
                        v-for="(item,i) in items"
                        :key="i"
                        :src="item.src"
                    >
                    <div class="title-carousel">
                        {{ item.text }}
                    </div>
                    </v-carousel-item>

                   </v-carousel>
               </v-row>
               <v-row v-else justify="center">
                   <v-col cols="10" >
                       <v-row justify="space-around" >
                           <v-col cols="3"  v-for="(item, index)  in items" :key="index">
                               <v-card >
                                   <v-img height="200" :src="item.src"></v-img>
                               </v-card>
                           </v-col>
                           
                       </v-row>
                   </v-col>
               </v-row>

               
               <v-row justify="space-between" align="center" >
                   
               </v-row>
                   
                <v-row align="center" justify="center" v-if="!isMobile">
                    <h1 class="display-1 my-12">Feijão,  Uma Historia</h1>
                    <v-col cols="12">
                        <v-row justify="center">
                            <v-col cols="5">
                                <p class="text-justify">
                                    O feijão-comum está entre os alimentos mais antigos do  mundo.  Seus  registros  estão   diretamente   asso-ciados  à  história  da  humanidade. No antigo Egito e   na   Grécia,   os   feijões   eram  cultivados  e  cultua-dos como símbolo da vida.
                                </p>
                            </v-col>
                            <v-col cols="5">
                                <p class="text-justify">
                                    No mundo da gastronomia 
                                    existem várias hipóteses 
                                    sobre o surgimento da feijoada. Uma das mais famosas diz que a feijoada que 
                                    conhecemos teve sua 
                                    origem no século XIX e já 
                                    se tornou símbolo nacional 
                                    na mesma época. Outra diz 
                                    que o prato foi criado nas 
                                    senzalas, pelos escravos, 
                                    usando restos de comida 
                                    dos nobres portugueses
                                </p>
                            </v-col>
                            <v-col cols="5">

                                <p class="text-justify">
                                    O feijão preto é de origem sul-americana  e  era  parte  da  dieta  dos  índios  nativos. Antes da chegada dos portugueses  ao  Brasil,  já  se  conhecia  na  Europa  diversas      variedades      de      feijão, e era comum usá-lo no    preparo    de    alguns    pratos,  como  “Cassoulet”  com o feijão branco.
                                </p>

                            </v-col>
                            <v-col cols="5">
                                <p class="text-justify">
                                    O  que  podemos  dizer  com  certeza  é  que  a  feijoada  é  uma  variação  de  um  prato  bem  antigo  típico  europeu,  que  tem como base a mistura de tipos diferentes  de  carne,  com  legumes  e  verduras, e varia de região em região. 
                                </p>
                            </v-col>
                        </v-row>

                </v-col>
            </v-row>
            <v-row align="center" justify="center" v-else>
                <v-col cols="12">
                        
                    <h1 class="display-1 my-4">Feijão,  Uma Historia</h1>
                    <p class="text-justify">
                        O feijão-comum está entre os alimentos mais antigos do  mundo.  Seus  registros  estão   diretamente   associados  à  história  da  humanidade. No antigo Egito e   na   Grécia,   os   feijões   eram  cultivados  e  cultuados como símbolo da vida.
                    </p>

                    <p class="text-justify">
                        O feijão preto é de origem sul-americana  e  era  parte  da  dieta  dos  índios  nativos. Antes da chegada dos portugueses  ao  Brasil,  já  se  conhecia  na  Europa  di-versas      variedades      de      feijão, e era comum usá-lo no    preparo    de    alguns    pratos,  como  “Cassoulet”  com o feijão branco.
                    </p>

                    <p class="text-justify">
                        No mundo da gastronomia 
                        existem várias hipóteses 
                        sobre o surgimento da feijoada. Uma das mais famosas diz que a feijoada que 
                        conhecemos teve sua 
                        origem no século XIX e já 
                        se tornou símbolo nacional 
                        na mesma época. Outra diz 
                        que o prato foi criado nas 
                        senzalas, pelos escravos, 
                        usando restos de comida 
                        dos nobres portugueses
                    </p>

                     <p class="text-justify">
                            O que  podemos  dizer  com  certeza  é  que  a  feijoada  é  uma  variação  de  um  prato  bem  antigo  típico  europeu,  que  tem como base a mistura de tipos diferentes  de  carne,  com  legumes  e  verduras, e varia de região em região. 
                    </p>
                </v-col>
            </v-row> 
           </v-container>
            

        </section>
    
</template>

<script>
export default {
    data: () => ({
        items : [
            {
            src: 'https://exame.com/wp-content/uploads/2020/06/bacon-in-natura.jpg',
            text: 'Bacon',
          },
          {
            src: 'https://cdn4.ecycle.com.br/cache/images/2018-10/50-650-filosofia-vegana.jpg',
            text: 'Vegano',
          },
          {
            src: 'https://d1uz88p17r663j.cloudfront.net/resized/bb8b6b5a95b117f0bd91bd12faab3ccc_charque-acebolado-receitas-nestle_1200_600.jpg',
            text: 'Charque',
          },
         
        ]
    }),

    computed: {
      isMobile() {
        switch (this.$vuetify.breakpoint.name) {
            case "xs":
                return true;
            case "sm":
                return true;
            default: 
                return false;
        }
      }
    }
}
</script>

<style>
    #historia {
        background: url("../assets/bg.jpeg");
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .title-carousel {
        height:200px;
        padding-bottom: 10px;
        box-sizing: border-box;
        display: flex;
        align-items: flex-end;
        justify-content: center;
        font-size: 20px;
        letter-spacing: 1px;
        text-transform: uppercase;
        font-weight: 900;
    }
</style>