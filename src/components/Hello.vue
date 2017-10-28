<template>
  <div style="width:100%">
    <get-address @input="reciveGeo"></get-address>
    <v-stepper v-model="realStep" class="elevation-0">
      <v-stepper-header class="elevation-0">
        <v-stepper-step step="1" :class="compare(1) ? 'stepper__step--active' : ''" :complete="realStep > 6">Qual a nescessidade?</v-stepper-step>
        <v-divider></v-divider>
        <v-stepper-step step="2" :class="compare(2) ? 'stepper__step--active' : 'not-active'" :complete="realStep > 8">Seus dados</v-stepper-step>
        <v-divider></v-divider>
        <v-stepper-step step="3" :class="compare(3) ? 'stepper__step--active' : 'not-active'">Pedido concluido!</v-stepper-step>
      </v-stepper-header>
      <v-stepper-content step="1">
          <v-container class="box-step">
            <v-layout row wrap>
              <v-flex xs12 class="titulo">
                Qual é o tipo de serviço que você precisa?
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Construção</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Reformas</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Instalações</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Troca</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Outros</v-btn>
              </v-flex>
            </v-layout>
          </v-container>
      </v-stepper-content>
      <v-stepper-content step="2">
          <v-container class="box-step">
            <v-layout row wrap>
              <v-flex xs12 class="titulo">
                Onde o serviço será feito?
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Construção em geral</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Forro</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Paredes e estruturas</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Pisos e revestimentos</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Outros</v-btn>
              </v-flex>
            </v-layout>
          </v-container>
        </v-stepper-content>
        <v-stepper-content step="3">
          <v-container class="box-step">
            <v-layout row wrap>
              <v-flex xs12 class="titulo">
                Qual o local?
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Casa</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Apartamento</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Comercial</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Lote de terreno</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Outro</v-btn>
              </v-flex>
            </v-layout>
          </v-container>
        </v-stepper-content>
        <v-stepper-content step="4">
          <v-container class="box-step">
            <v-layout row wrap>
              <v-flex xs12 class="titulo">
                Quais são as medidas?
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Pequeno (até 50m²)</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Médio (de 50 a 150 m²)</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Grande (mais de 150 m²)</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Não tenho certeza</v-btn>
              </v-flex>
            </v-layout>
          </v-container>
        </v-stepper-content>
        <v-stepper-content step="5">
          <v-container class="box-step">
            <v-layout row wrap>
              <v-flex xs12 class="titulo">
                Para quando você precisa deste serviço?
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">O quanto antes possível</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Nos próximos 30 dias</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Nos próximos 3 meses</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Não tenho certeza</v-btn>
              </v-flex>
            </v-layout>
          </v-container>
        </v-stepper-content>
        <v-stepper-content step="6">
          <v-container class="box-step">
            <v-layout row wrap>
              <v-flex xs12 class="titulo">
                Para quando você precisa deste serviço?
              </v-flex>
              <v-flex xs12>
                <v-text-field
                  name="input-7-1"
                  label="Descreva o que você precisa"
                  multi-line
                ></v-text-field>
              </v-flex>
              <div v-show="isPortador" style="width:100%">
                <v-flex xs12>
                  <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="selectItem">Visual</v-btn>
                </v-flex>
                <v-flex xs12>
                  <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="selectItem">Auditiva</v-btn>
                </v-flex>
                <v-flex xs12>
                  <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="selectItem">Motora</v-btn>
                </v-flex>
                <v-flex xs12>
                  <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="selectItem">Intelectual</v-btn>
                </v-flex>
              </div>
             <v-flex xs6>
               <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Prosseguir</v-btn>
            </v-flex>
            <v-flex xs12>
              <v-checkbox label="Portador de deficiencia?" v-model="isPortador"></v-checkbox>
            </v-flex>
            </v-layout>
          </v-container>
          <v-btn color="primary" v-show="e1 > 0" @click.native="goBack">Voltar</v-btn>
      </v-stepper-content>
      <v-stepper-content step="7">
          <v-container>
            <v-layout row wrap>
              <v-flex xs12>
                <p>
                  Encontramos
                </p>
                <div class="destaque-quantidade">
                  72
                </div>
                <p>
                  profissionais na região de
                </p>
                <p>
                  <strong>{{ geolocation }}</strong>
                </p>
               </v-flex>
               <v-flex xs12 class="">
                 realizar o serviço em outro lugar?
                </v-flex>
                <v-flex xs12 class="">
                  proximo
                 </v-flex>
             <v-flex offset-xs6 xs6>
               <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Prosseguir</v-btn>
            </v-flex>
            </v-layout>
          </v-container>
        </v-stepper-content>
        <v-stepper-content step="8">
        <v-container>
          <v-layout row wrap>
            <v-flex xs12>
              <img src="https://www.getninjas.com.br/assets/request/phone_call.svg" alt="">
             </v-flex>
             <v-flex xs12 class="">
               realizar o serviço em outro lugar?
             </v-flex>
             <v-flex xs12 class="">
              Não perca tempo ligando para vários profissionais. Preencha os dados abaixo e nós encontraremos os melhores pra você!
             </v-flex>
             <v-flex offset-xs6 xs6>
               <v-btn block class="elevation-1 text-xs-left back-btn" @click.native="changeView2">Prosseguir</v-btn>
            </v-flex>
          </v-layout>
        </v-container>
      </v-stepper-content>
      <v-stepper-content step="9">
        <v-btn color="primary" @click.native="e1 = 1">Continue</v-btn>
        <v-btn flat>Cancel</v-btn>
      </v-stepper-content>
    </v-stepper>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      realStep: 1,
      e1: 0,
      isPortador: false,
      percent: 7,
      query: false,
      show: true,
      geolocation: ''
    }
  },
  methods: {
    changeView2 () {
      // this.e1 = this.e1 + 1
      // if (this.e1 === 6 || this.e1 === 7 ) {
        this.realStep = this.realStep + 1
      // }
      // this.percent = 15
    },
    goBack () {
      this.e1 = this.e1 - 1
    },
    reciveGeo (geolocation) {
      this.geolocation = geolocation
    },
    compare (value) {
      if (this.realStep < 7 && value === 1) {
        return true
      }
      if (this.realStep > 6 && value === 2) {
        return true
      }
      if (this.realStep > 8 && this.realStep < 11 && value === 3) {
        return true
      }
      return false
    }
  },
  mounted () {
    console.log(this.compare(1))
    console.log(this.compare(2))
    console.log(this.compare(3))
  },
  components: {
    'get-address': require('./GetAddress.vue')
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
h1, h2 {
  font-weight: normal;
}
.stepper__content{
  min-height: 300px;
}
.stepper__step--complete span{
  background: green!important;
}
.color-green{
  color: green;
}
.float-right{
  float: right;
}
.not-active .stepper__step__step{
  background-color: rgba(0,0,0,0.38)!important
}
ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #35495E;
}
</style>
