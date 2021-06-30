<template>
  <v-main>
    <v-expand-transition>
      <v-app-bar color="white" v-show="expandBar2">
        <a @click="showHome">
          <v-img
              alt="Logo"
              class="shrink mr-2"
              contain
              src="../assets/huitzil.png"
              transition="scale-transition"
              width="60"></v-img>
        </a>
        <a @click="showHome" class="a-title">
          <v-toolbar-title>HUITZIL</v-toolbar-title>
        </a>
        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon>mdi-help</v-icon>
          </v-btn>
      </v-app-bar>
    </v-expand-transition>
    <p></p>

    <v-container>

      <v-expand-transition>
        <div v-show="expandBar"> 
          <v-row class="text-center">

            <v-col cols="6">
              <v-card
                  color="blue lighten-1"
                  dark
                  @click="showActivity(1)"
                >
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <div>
                      <v-card-title
                        class="text-h5v"
                      >Memorama de<br> multiplicaciones</v-card-title>

                      <v-card-subtitle></v-card-subtitle>

                      <v-card-actions>
                        <v-btn
                          class="ml-2 mt-3"
                          fab
                          icon
                          height="60px"
                          right
                          width="60px"
                        >
                          <v-icon>mdi-play</v-icon>
                        </v-btn>

                      </v-card-actions>
                    </div>

                    <v-avatar
                      class="ma-3"
                      size="125"
                      tile
                    >
                      <v-img src="../assets/thumb1.png"></v-img>
                    </v-avatar>
                  </div>
                </v-card>
            </v-col>

            <v-col cols="6">
              <v-card
                  color="teal lighten-1"
                  dark
                  @click="showActivity(2)"
                >
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <div>
                      <v-card-title
                        class="text-h5v"
                      >¿Cuántas ruedas<br> se necesitan?</v-card-title>

                      <v-card-subtitle></v-card-subtitle>

                      <v-card-actions>
                        <v-btn
                          class="ml-2 mt-3"
                          fab
                          icon
                          height="60px"
                          right
                          width="60px"
                        >
                          <v-icon>mdi-play</v-icon>
                        </v-btn>

                      </v-card-actions>
                    </div>

                    <v-avatar
                      class="ma-3"
                      size="125"
                      tile
                    >
                      <v-img src="../assets/thumb2.png"></v-img>
                    </v-avatar>
                  </div>
                </v-card>
            </v-col>
          </v-row>

          <v-row class="text-center">

            <v-col cols="6">
              <v-card
                  color="deep-orange lighten-1"
                  dark
                  @click="showActivity(3)"
                >
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <div>
                      <v-card-title
                        class="text-h5v"
                      >Medios, cuartos <br>y octavos</v-card-title>

                      <v-card-subtitle></v-card-subtitle>

                      <v-card-actions>
                        <v-btn
                          class="ml-2 mt-3"
                          fab
                          icon
                          height="60px"
                          right
                          width="60px"
                        >
                          <v-icon>mdi-play</v-icon>
                        </v-btn>

                      </v-card-actions>
                    </div>

                    <v-avatar
                      class="ma-3"
                      size="125"
                      tile
                    >
                      <v-img src="../assets/thumb3.png"></v-img>
                    </v-avatar>
                  </div>
                </v-card>
            </v-col>

            <v-col cols="6">
              <v-card
                  color="green lighten-1"
                  dark
                  @click="showActivity(4)"
                >
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <div>
                      <v-card-title
                        class="text-h5v"
                      >Saltando sobre<br> el puente</v-card-title>

                      <v-card-subtitle></v-card-subtitle>

                      <v-card-actions>
                        <v-btn
                          class="ml-2 mt-3"
                          fab
                          icon
                          height="60px"
                          right
                          width="60px"
                        >
                          <v-icon>mdi-play</v-icon>
                        </v-btn>

                      </v-card-actions>
                    </div>

                    <v-avatar
                      class="ma-3"
                      size="125"
                      tile
                    >
                      <v-img src="../assets/thumb4.png"></v-img>
                    </v-avatar>
                  </div>
                </v-card>
            </v-col>
          </v-row>

          <v-row class="text-center" align="center">
            <v-col cols="6">
              <v-btn color="teal lighten-1" block class="bp" dark>
                Ayuda
              </v-btn>
            </v-col>
            <v-col cols="6">
              <v-btn color="lime darken-1" block dark class="no-up">
                Salir
              </v-btn>
            </v-col>            
          </v-row>

        </div>
      </v-expand-transition> 

      <v-expand-transition>
        <div class="activity" v-show="expandActivity">
          <Memorama :key="keyMem"/>

          <!--
          <v-card-text style="height: 100px; position: relative">
              <v-fab-transition>
                <v-btn
                  v-show="!hiddenBtn"
                  color="blue"
                  class="no-up"
                  dark
                  absolute
                  bottom
                  left
                  fab
                  @click="showActivity()"
                >
                  <v-icon>mdi-home</v-icon>
                </v-btn>
              </v-fab-transition>
            </v-card-text>

            <v-card-text style="height: 100px; position: relative; margin-top: -100px">
              <v-fab-transition>
                <v-btn
                  v-show="!hiddenBtn"
                  color="green"
                  class="no-up"
                  dark
                  absolute
                  bottom
                  right
                  fab
                  @click="showHelp()"
                >
                  <v-icon>mdi-help</v-icon>
                </v-btn>
              </v-fab-transition>
            </v-card-text> -->
        </div>
      </v-expand-transition>

    </v-container>
  </v-main>
</template>

<script>
import Memorama from '@/components/Memorama.vue'

export default {
  name: "StartMenu",

  components: {
    Memorama
  },

  data: () => ({
    keyMem: 1,
    expandBar: true,
    expandBar2: true,
    expandCards: true,
    expandActivity: false,
    hiddenBtn: true,
    activityNumber: 1,
  }),

  methods: {
    showActivity(a) {
      this.expandBar =! this.expandBar
      this.expandActivity =! this.expandActivity
      /*setTimeout(() => {
        this.hiddenBtn =! this.hiddenBtn
      }, 400);*/
      this.activityNumber = a
    },

    showHome() {
      this.expandBar = true
      this.expandActivity = false
      this.keyMem++
    }
  },
}
</script>

<style scoped>

.a-title {
  color:  #414141;
}
.no-up {
  text-transform: none;
}
.bp {
  text-transform: capitalize;
  color: #fff;
}
.text-h5v {

}
.v-speed-dial {
    position: absolute;
  }
.v-btn--floating {
    position: relative;
  }
</style>