<template>
<v-parallax height="700" dark src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg">
 <v-container >
  <div class="about" >
   
    <h1>Datos de envio</h1>

    <v-form
    dark
    ref="form"
    v-model="valid"
    lazy-validation>

      <v-text-field
      dark
      v-model="name"
      :rules="nameRules"
      label="Nombre Completo"
      required>

      </v-text-field>

      <v-text-field
      dark
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required>        
      </v-text-field>

      <v-text-field
      dark
      v-model="codigoPostal"
      :rules="codigoPostalRules"
      label="código postal"
      type="number"
      required>

      </v-text-field>

        <v-text-field
      dark
      v-model="Calle"
      :rules="callerules"
      label="Calle"
      required>

      </v-text-field>

      <v-select
      dark
      v-model="País"
      :rules="paísrules"
      label="País"
      required>

      </v-select>

      <v-select
      dark
      v-model="Estado"
      :rules="estadorules"
      label="Estado"
      required>

      </v-select>

      <v-select
      dark
      v-model="Ciudad"
      :rules="ciudadrules"
      label="Ciudad"
      required>

      </v-select>

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
    email:'',
    emailRules:[
      v => !!v || 'Se requiere un email'
    ],
    codigoPostal:'',
    codigoPostalRules:[
      v => !!v || 'Se requiere un código postal',
      v => (v && v.length <= 5) || 'Ingrese un código postal válido' 
    ],
    Calle:'',
    callerules:[
      v => !!v || 'Se requiere una Calle',
    ],
    Ciudad:'',
    ciudadrules:[
      v => !!v || 'Se requiere una Ciudad',
    ],
    Estado:'',
    estadorules:[
      v => !!v || 'Se requiere un estado',
    ],
    País:'',
    paísrules:[
      v => !!v || 'Se requiere un pais',
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

