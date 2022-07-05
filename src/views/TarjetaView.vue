<template>
<v-parallax height="600" dark src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg">
 <v-container >
  <div class="about" >
   
    <h1>Datos de la tarjeta</h1>

    <v-form
    dark
    ref="form"
    v-model="valid"
    lazy-validation>

      <v-text-field
      dark
      v-model="name"
      :rules="nameRules"
      label="Nombre completo"
      required>

      </v-text-field>


      <v-text-field
      dark
      v-model="NumeroTarjeta"
      :rules="NumeroTarjetaRules"
      label="Numero de tarjeta"
      type="number"
      required>

      </v-text-field>

        <v-col cols="9">
        <div style="max-width: 300px">
        CVV : 
       <v-otp-input
      dark
      v-model="CVVTarjeta"
      :rules="CVVRules"
      length="4"
      label="CVV"
       type="password"
      required>

      </v-otp-input>
      </div>
</v-col>
      <v-checkbox
      dark
      v-model="checkbox"
      :rules="[v => !!v || 'Debes estar de acuerdo para continuar']"
      label="Estas de acuerdo"
      required>

      </v-checkbox>

      

      <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate">
        Validar
      </v-btn>

      <v-btn
      color="error"
      class="mr-4"
      @click="reset">
        Resetear
      </v-btn>
    </v-form>

  </div>
  </v-container>
  </v-parallax>
</template>

<script>
export default{
  data:() =>({
    valid:true,
    name:'',
    nameRules:[
      v => !!v || 'Se require un nombre'
    ],
    NumeroTarjeta:'',
    NumeroTarjetaRules:[
      v => !!v || 'Se requiere un numero de tarjeta',
    v => (v && v.length === 18) || 'Ingrese un numero de tarjeta válido' 
    ],
    CVVTarjeta:'',
    CVVRules:[
      v => !!v || 'Se requiere un CVV',
      v => (v && v.length === 4) || 'Ingrese un cvv válido' 
    ],
    checkbox:false,

  }),
  methods:{
    validate (){
      this.$refs.form.validate()
    },
    reset(){
      this.$refs.form.reset()
    }
  }
}

</script>