<template>
<v-parallax height="600" dark src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg">
    <v-container class="mt-4">
        <v-row>
            <v-col xs12 cols="4">
                <v-card class="mx-auto"  max-width="344">

                    <v-img src="https://ss632.liverpool.com.mx/xl/1112820252.jpg" ></v-img>

                </v-card>

            </v-col>

            <v-col xs6 cols="8">
                <v-card dark style=" background-image:url('https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg')">

                    <v-card-tittle>
                        <h1 class="text-center">
                            Smartphone Motorola G60 6GB RAM 128GB ROM Azul
                        </h1>
                    </v-card-tittle>
                    <v-card-subtitle>
                        <h3> Marca <span class="azul">Motorola</span></h3>
                        <h2>$4,600.00</h2>
                    </v-card-subtitle>
                        <v-divider class="mx-4"></v-divider>
                    <v-card-text>
                        <div>
                        Vendido por <span class="azul">GCMóvil</span>
                        <v-spacer></v-spacer>
                        <span class="azul" >Consultar garantía</span>
                        </div>

                        
                            <tr>
                                <td>
                               - Pantalla 6.8 pulgadas.
                                </td>
                            </tr>
                            <tr>
                                <td>
                               - Batería 6,000 mah.
                                </td>
                            </tr>
                            <tr>
                                <td>
                               - Cámara trasera: 108 + 8 + 2 mp
                                </td>
                            </tr>
                   
                    </v-card-text>

                    <v-cart-text>
                        <v-btn block x-large color="success">

                        Comprar

                        </v-btn>
                    </v-cart-text>


                    

                </v-card>
            </v-col>
        </v-row>

    </v-container>
</v-parallax>
</template>

<script>


export default {
  

  data: () => ({
   
  }),
  components: {
    

  }
};


</script>

<style>

.azul{
    color: rgb(65, 192, 75);
}


</style>