<template>
  <v-app>
    <div>
      <v-toolbar dark src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg">
        <v-app-bar-nav-icon @click="drawer = !drawer" large></v-app-bar-nav-icon>

        <v-toolbar-title >
          <router-link to="/">
            <v-icon large>mdi-cellphone</v-icon>
            <span class="icono" >Tienda motorola</span>
          </router-link>
        </v-toolbar-title>
        
        <v-spacer></v-spacer>
        <router-link to="/Carrito">
           <v-badge
           :content="carritoNumero"
          :value="carritoNumero"
          color="green"
          overlap>
          <v-btn icon>
            <v-icon left large>mdi-cart</v-icon>
          </v-btn>
           </v-badge>

       
        </router-link>
        <v-btn class="mx-1" color="primary" @click="carritoNumero++">

            agregar la carrito

        </v-btn>

        <v-btn class="mx-1" color="error" @click="carritoNumero = 0">
            Quitar del carrito
        </v-btn>
      </v-toolbar>

    </div>

    <v-navigation-drawer app v-model="drawer" temporary dark
      src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg">
      <v-list>
        <v-list-item class="px-2">
          <v-list-item-avatar>
            <v-icon large>mdi-account-circle</v-icon>
          </v-list-item-avatar>
        </v-list-item>

        <v-list-item link>
          <v-list-item-content>
            <v-list-item-title class="text-h6">
              Usuario
            </v-list-item-title>
            <v-list-item-subtitle>Iniciar sesión/registrarse</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider></v-divider>

      <v-list dense nav>

        <v-list-item v-for="item in items" :key="item.tittle" link>

          <router-link to="/">
            <v-icon class="mr-3">{{ item.icon1 }}</v-icon><span class="icono" >{{ item.tittle1 }}</span>
          </router-link>

          <router-link to="Carrito">
            <v-icon class="mr-3">{{ item.icon2 }}</v-icon><span class="icono" >{{ item.tittle2 }}</span>
          </router-link>

          <router-link to="/Registro">
            <v-icon class="mr-3">{{ item.icon3 }}</v-icon><span class="icono" >{{ item.tittle3 }}</span>
          </router-link>

          <router-link to="/Tarjeta">
            <v-icon class="mr-3">{{ item.icon4 }}</v-icon><span class="icono" >{{ item.tittle4 }}</span>
          </router-link>

        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <router-view />
    </v-main>

  </v-app>
</template>

<script>



export default {
  name: 'MenuPrincipal',
   props: ['Numero'],

  data: () => ({
    drawer: true,
    carritoNumero:0,
    items: [
      { tittle1: 'Inicio', icon1: 'mdi-home' },
      { tittle2: 'Carrito', icon2: 'mdi-cart' },
      { tittle3: 'Registro', icon3: 'mdi-account-box' },
      { tittle4: 'Tarjeta', icon4: 'mdi-account-box' }

    ],
  }),
  components: {

}
};
</script>

<style >

.icono{
  color: beige;
}
</style>