<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer">
      <!-- Interior do menu -->
    </v-navigation-drawer>

    <v-app-bar elevation="0">
      <!-- <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon> -->
      <v-container>
        <h2 class="pl-3">Home</h2>
      </v-container>
    </v-app-bar>

    <v-main>
      <v-container>
        <v-row class="pl-3" no-gutters>
          <v-col class="d-flex justify-start" cols="3">
            <v-avatar class="avatar" size="80"></v-avatar>
          </v-col>
          <v-col cols="8" class="pl-2 pt-2">
            <h3 class="mb-2">Luiz Gouveia</h3>
            <v-row id="ultimaCorrida" no-gutters>
              <v-col cols="1">
                <v-img
                  contain
                  height="19px"
                  width="19px"
                  src="./public/runner.png"
                >
                </v-img>
              </v-col>
              <v-col cols="4" class="d-flex justify-center">
                <h5>Corrida</h5>
              </v-col>
              <v-col cols="1" class="d-flex pt-1">
                <v-img
                  src="./public/diamond.png"
                  contain
                  height="9px"
                  width="9px"
                >
                </v-img>
              </v-col>
              <v-col cols="6" class="d-flex justify-center">
                <h5>Hoje às 10hrs</h5>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
      <v-container class="pt-2 pb-2">
        <v-row>
          <v-col>
            <h2 class="pl-3">Corrida Matinal</h2>
          </v-col>
        </v-row>
      </v-container>
      <v-container>
        <v-row>
          <v-col id="map" cols="7" class="ml-6"></v-col>
          <v-col cols="4" class="mr-0 pr-0 d-flex flex-column">
            <h3>10,05 km</h3>
            <h4>Distância</h4>
            <v-spacer class="pb-3"></v-spacer>
            <h3>45:10</h3>
            <h4>Duração</h4>
            <v-spacer class="pb-3"></v-spacer>
            <h3>6:45/km</h3>
            <h4>Média/Ritmo</h4>
          </v-col>
        </v-row>
        <v-row class="d-flex justify-center mt-7">
          <v-col
            id="infoSaude"
            v-for="n in 4"
            :key="n"
            cols="5"
            class="d-flex justify-start ma-2"
          >
            <v-row>
              <v-col cols="4" class="d-flex">
                <v-img
                  contain
                  height="19px"
                  width="19px"
                  src="./public/runner.png"
                >
                </v-img>
              </v-col>
              <v-col cols="8">
                <h4 class="d-flex justify-start">Passos</h4>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    user: {
      image: "./public/asspublic/small-profilepic.png",
      nome: "Luiz Gouveia",
      corrida: "true",
    },
    infoHealth: {
      running: {
        icon: "./public/asspublic/runner.png",
        title: "Passos",
        result: "2.500 passos",
        percentuageOfGopublic: "50%",
      },
      cycling: {
        icon: "./public/asspublic/rider.png",
        title: "Pedaladas",
        result: "19.000 pedaladas",
        percentuageOfGoapublic: "85%",
      },
      water: {
        title: "Água",
        liters: "2 litros",
      },
      calorpublic: {
        title: "Calorias",
        pointer: "Under",
      },
      healthRate: {
        title: "Cardio",
        bpm: "110",
      },
    },
    drawer: null,
  }),
};
</script>

<style scoped>
#userInfo {
  font-size: 16px;
}

h2 {
  font-weight: 700;
  font-size: 1.3rem;
}

.avatar {
  background-image: url("./public/small-profilepic.png");
  background-size: cover;
  background-position: center;
}

.userInfoText {
  padding-top: 0.2rem;
  padding-left: 1.2rem;
}

h5,
h4,
#ultimaCorrida {
  font-weight: 600;
  color: var(--color-text-light);
  font-size: 14.5px;
  line-height: 18px;
  opacity: 80%;
}

#map {
  background-color: #35b36750;
  height: 25vh;
  border-radius: 25px;
}

#infoSaude {
  height: 15vh;
  border: solid 1px #28282849;
}

#infoSaude h4 {
  color: var(--color-text-dark);
  font-family: "Tenby-five", sans-serif;
}
</style>
