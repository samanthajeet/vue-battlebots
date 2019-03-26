<template>
  <div>
    {{this.bot1}}
    {{this.bot2}}
    <button> BATTLE </button>
    <button @click='onClear'> CLEAR </button>
    <bot v-for='(botObj, i) in this.allBots' :key='i' :botObj='botObj' :index='i' :retireBot='retireBot' :onSelect='onSelect' />
  </div>
</template>

<script>

import Bot from './Bot'

export default {
  props: ['allBots'],
  data: function(){
    return {
      bot1: [],
      bot2: []
    }
  },

  methods: {
    retireBot: function(index){
      console.log(index)
      this.allBots.splice(index,1)
    },
    onSelect: function(bot) {
      if(this.bot1.length === 0){
        this.bot1 = bot
      } else {
        this.bot2 = bot
      }
    },
    onClear: function(){
      this.bot1 = []
      this.bot2 = []
    }
    
  },
  components: { Bot : Bot}
  
}
</script>

