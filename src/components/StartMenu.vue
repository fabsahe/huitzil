<template>
  <v-main>
    <v-expand-transition>
      <v-app-bar color="white" v-show="expandBar">
        <v-img
            alt="Logo"
            class="shrink mr-2"
            contain
            src="../assets/huitzil.png"
            transition="scale-transition"
            width="60"></v-img>
        <v-toolbar-title>HUITZIL</v-toolbar-title>
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
            <v-col cols="2">
            </v-col>
            <v-col cols="4">
              <v-card
                  color="blue lighten-1"
                  dark
                  @click="showActivity(1)"
                >
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <div>
                      <v-card-title
                        class="text-h5"
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

            <v-col cols="4">
              <v-card
                  color="teal lighten-1"
                  dark
                  @click="showActivity(2)"
                >
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <div>
                      <v-card-title
                        class="text-h5"
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
            <v-col cols="2"></v-col>
            <v-col cols="4">
              <v-card
                  color="deep-orange lighten-1"
                  dark
                  @click="showActivity(3)"
                >
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <div>
                      <v-card-title
                        class="text-h5"
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

            <v-col cols="4">
              <v-card
                  color="green lighten-1"
                  dark
                  @click="showActivity(4)"
                >
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <div>
                      <v-card-title
                        class="text-h5"
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
        </div>
      </v-expand-transition> 

      <v-expand-transition>
        <div class="activity" v-show="expandActivity">
          <h1>ACTIVIDAD {{ activityNumber }}</h1>

          <v-card-text style="height: 100px; position: relative">
              <v-fab-transition>
                <v-btn
                  v-show="!hiddenBtn"
                  color="blue"
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
            </v-card-text>
        </div>
      </v-expand-transition>

    </v-container>
  </v-main>
</template>

<script>

export default {
  name: "StartMenu",

  data: () => ({
    expandBar: true,
    expandCards: true,
    expandActivity: false,
    hiddenBtn: true,
    activityNumber: 1,
  }),

  methods: {
    showActivity(a) {
      this.expandBar =! this.expandBar
      this.expandActivity =! this.expandActivity
      setTimeout(() => {
        this.hiddenBtn =! this.hiddenBtn
      }, 400);
      this.activityNumber = a
    }
  },
}
</script>

<style>
.v-speed-dial {
    position: absolute;
  }
.v-btn--floating {
    position: relative;
  }
</style>