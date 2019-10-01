<template>
  <div>
    <v-container v-if="alphabet" class="grey lighten-5">
    <v-row class="mb-12" no-gutters>
      <v-col class="center-text">
        <div class="help-text" v-if="!letter.letter">
          Denne app viser arabiske bogstaver i tilfældig rækkefølge.
        </div>
        <div class="arabic-letter" v-bind:class="{ active: letter.light && showHelp }">
          {{letter.letter}}
        </div>
        <div v-if="showHelp" class="help-text">{{letter.description}}</div>
        <div v-if="showHelp">({{letter.light ? 'Lys betoning': 'Dyb betoning'}})</div>
      </v-col>
    </v-row>
  </v-container>
   <v-bottom-navigation v-model="bottomNav">
      <v-btn @click="generateRandomLetter()" value="favorites">
        <span>{{letter.letter ? 'NÆSTE BOGSTAV' : 'VIS FØRSTE BOGSTAV'}}</span>
      </v-btn>

      <v-btn v-if="letter.letter" @click="showHelp = !showHelp" value="recent">
        <span>{{showHelp ? 'FJERN HJÆLP' : 'VIS HJÆLP'}}</span>
      </v-btn>
    </v-bottom-navigation>    
  </div>
</template>

<script>
export default {
  name: 'RandomArabicLetters',
  data: function() {
		return {
      bottomNav: 'recent',
      showHelp: false,
      letter: {},
      alphabet: [
        {
          letter:"أ",
          light: true,
          description: "alif"
        },
        {
          letter:"ب",
          light: true,
          description: "Baa"
        },
        {
          letter:"ت",
          light: true,
          description: "Taa"
        },
        {
          letter:"ث",
          light: true,
          description: "Thaa"
        },
        {
          letter:"ج",
          light: true,
          description: "Jeem"
        },
        {
          letter:"ج",
          light: true,
          description: "Haa"
        },
        {
          letter:"خ",
          light: false,
          description: "Khaa"
        },
        {
          letter:"د",
          light: true,
          description: "Daal"
        },
        {
          letter:"ذ",
          light: true,
          description: "Dhaal"
        },
        {
          letter:"ر",
          light: false,
          description: "Raa"
        },
        {
          letter:"ز",
          light: true,
          description: "Zaa"
        },
        {
          letter:"س",
          light: true,
          description: "Seen"
        },
        {
          letter:"ش",
          light: true,
          description: "Sheen"
        },
        {
          letter:"ص",
          light: false,
          description: "Saad"
        },
        {
          letter:"ض",
          light: false,
          description: "Daad"
        },
        {
          letter:"ط",
          light: false,
          description: "Taa"
        },
        {
          letter:"ظ",
          light: false,
          description: "Thaa"
        },
        {
          letter:"ع",
          light: true,
          description: "'Ayn"
        },
        {
          letter:"غ",
          light: false,
          description: "Ghayn"
        },
        {
          letter:"ف",
          light: true,
          description: "Faa"
        },
        {
          letter:"ق",
          light: false,
          description: "Qaaf"
        },
        {
          letter:"ك",
          light: false,
          description: "Kaaf"
        },
        {
          letter:"ل",
          light: true,
          description: "Laam"
        },
        {
          letter:"م",
          light: true,
          description: "Meem"
        },
        {
          letter:"ن",
          light: true,
          description: "Nuun"
        },
        {
          letter:"ه",
          light: true,
          description: "Haa'"
        },
        {
          letter:"و",
          light: true,
          description: "Waaw"
        },
        {
          letter:"ي",
          light: true,
          description: "Yaa'"
        }
      ]
    }
  },
  methods: {
    generateRandomLetter: function () {
      const min = 0;
      const max = 27;
      const random = Math.floor(Math.random() * (+max - +min)) + +min;
      this.letter = this.alphabet[random];
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css?family=Markazi+Text&display=swap');
h3 {
  margin: 40px 0 0;
}

.help-text{
  font-size: 50px;
}

.arabic-letter{
  font-family: 'Markazi Text', serif!important;
  font-size: 320px;
  color: black;
}

.center-text{
  text-align: center;
}

.v-bottom-navigation{
  position: fixed;
}

.active{
  color: #42b983;
}

</style>
