<template>
  <v-app light>
    <main>
      <v-container fluid class="ma-0 pa-0">
          <v-layout row wrap class="elevation-1">
            <v-container fluid class="barra-topo">
              <v-layout row wrap>
                <v-flex xs2 class="voltar">
                  back
                </v-flex>
                <v-flex xs8 class="text-xs-center">
                  Precisando de Pedreiros?
                </v-flex>
                <v-flex xs2>
                  question
                </v-flex>
              </v-layout>
            </v-container>
          </v-layout>
          <v-layout row wrap>
            <v-flex xs10 offset-xs1 mt-3 mb-3>
              Milhares de profissionais avalidados por clientes,
              permitindo você negociar apenas com os melhores.
            </v-flex>
            <v-flex xs10 offset-xs1 class="text-xs-left">
              <img src="https://www.getninjas.com.br/assets/categories/stamp-safe-9227a11c823097593417e5aebfd1813a9ec574fb600c05a58078b6a65c7c6ff6.svg" class="gratis" height="30" width="30" alt="Selo de segurança">
              <span class="pl-2" style="font-size:16px; margin-top:-10px;font-style: italic;font-color: #828282;">Grátis e Seguro</span>
            </v-flex>
          </v-layout>
          <v-layout row wrap>
            <v-container fluid>
              <v-slide-y-transition mode="out-in">
                <v-layout column align-center>
                  <router-view></router-view>
                </v-layout>
              </v-slide-y-transition>
            </v-container>
          </v-layout>
      </v-container>
    </main>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        clipped: false,
        drawer: true,
        fixed: false,
        items: [
          { icon: 'bubble_chart', title: 'Inspire' }
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'Vuetify.js'
      }
    }
  }
</script>
<style media="screen">
.gratis{
  position: relative;
  top: 8px;
}

</style>
