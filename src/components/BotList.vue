<template>
  <div class='botlist'>
    <h4>
      Bot #1 : <span class='bot1'> {{this.bot1.botName}}</span>
      <!-- {{this.bot1}} -->
    </h4>
    <h4>
      Bot #2 : <span class='bot2'> {{this.bot2.botName}}</span>
      <!-- {{this.bot2}} -->
    </h4>

      <button @click='battle' class='botlistbtn'> battle </button>
      <button @click='onClear' class='botlistbtn'> clear </button>

    <secion class='bots'>
      <bot v-for='(botObj, i) in this.allBots' :key='i' :botObj='botObj' :index='i' :retireBot='retireBot' :onSelect='onSelect' />
    </secion>
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
    },
    battle: function(){
      if(this.bot1.attackVal > this.bot2.attackVal){
        alert(`${this.bot1.botName} wins!`)
      } else {
        alert(`${this.bot2.botName} wins!`)
      }
      this.bot1 = []
      this.bot2 = []
    }
  },
  components: { Bot : Bot}
  
}
</script>

