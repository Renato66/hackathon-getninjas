<template>
  <div style="width:100%">
    <v-stepper v-model="realStep">
      <v-stepper-header>
        <v-stepper-step step="1" :complete="e1 > 2">Name of step 1</v-stepper-step>
        <v-divider></v-divider>
        <v-stepper-step step="2" :complete="e1 > 4">Name of step 2</v-stepper-step>
        <v-divider></v-divider>
        <v-stepper-step step="3">Name of step 3</v-stepper-step>
      </v-stepper-header>
      <v-stepper-content step="1">
        <v-slide-x-transition mode="out-in">
          <v-container v-show="e1 === 0">
            <v-layout row wrap>
              <v-flex xs12>
                <v-btn flat block color="primary" @click.native="changeView2">Pedreiro</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn flat block color="primary" @click.native="changeView2">algo</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn flat block color="primary" @click.native="changeView2">Continue</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn flat block color="primary" @click.native="changeView2">cancela</v-btn>
              </v-flex>
            </v-layout>
          </v-container>
        </v-slide-x-transition>
        <v-slide-x-transition mode="in-out">
          <v-container v-show="e1 === 1">
            <v-layout row wrap>
              <v-flex xs12>
                <v-btn flat block color="primary" @click.native="changeView2">cidade</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn flat block color="primary" @click.native="changeView2">algo</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn flat block color="primary" @click.native="changeView2">aaaaa</v-btn>
              </v-flex>
            </v-layout>
          </v-container>
        </v-slide-x-transition>
        <v-slide-x-transition mode="in-out">
          <v-container v-show="e1 === 2">
            <v-layout row wrap>
              <v-flex xs12>
                <v-btn flat block color="primary" @click.native="changeView2">oddsdosk</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn flat block color="primary" @click.native="changeView2">algo</v-btn>
              </v-flex>
              <v-flex xs12>
                <v-btn flat block color="primary" @click.native="changeView2">aaaaa</v-btn>
              </v-flex>
            </v-layout>
          </v-container>
        </v-slide-x-transition>

        <v-btn color="primary" v-show="e1 > 0" @click.native="goBack">Voltar</v-btn>
      </v-stepper-content>
      <v-stepper-content step="2">
        <v-container >
          <v-layout row wrap>
            <v-flex xs12>
              <v-btn flat block color="primary" @click.native="changeView2">Pedreiro</v-btn>
            </v-flex>
            <v-flex xs12>
              <v-btn flat block color="primary" @click.native="changeView2">algo</v-btn>
            </v-flex>
            <v-flex xs12>
              <v-btn flat block color="primary" @click.native="changeView2">Continue</v-btn>
            </v-flex>
            <v-flex xs12>
              <v-btn flat block color="primary" @click.native="changeView2">cancela</v-btn>
            </v-flex>
          </v-layout>
        </v-container>
      </v-stepper-content>
      <v-stepper-content step="2">
        <v-btn color="primary" @click.native="e1 = 3">Continue</v-btn>
        <v-btn flat>Cancel</v-btn>
      </v-stepper-content>
      <v-stepper-content step="3">
        <v-btn color="primary" @click.native="e1 = 1">Continue</v-btn>
        <v-btn flat>Cancel</v-btn>
      </v-stepper-content>
      <div class="pa-2">
        <div class="color-green float-right">
          {{ percent }}%
        </div>
        <v-progress-linear
        v-bind:indeterminate="query"
        v-bind:query="true"
        v-model="percent"
        v-bind:active="show"
        ></v-progress-linear>
      </div>
    </v-stepper>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      realStep: 0,
      e1: 0,
      percent: 7,
      query: false,
      show: true
    }
  },
  methods: {
    changeView2 () {
      this.e1 = this.e1 + 1
      if (this.e1 > 2) {
        this.realStep = this.realStep + 1
      }
      this.percent = 15
    },
    goBack () {
      this.e1 = this.e1 - 1
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
h1, h2 {
  font-weight: normal;
}
.stepper__content{
  height: 300px;
}
.color-green{
  color: green;
}
.float-right{
  float: right;
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
