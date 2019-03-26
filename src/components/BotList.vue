<template>
  <div>
    <bot v-for='(botObj, i) in this.allBots' :key='i' :botObj='botObj' :index='i' :retireBot='retireBot' />
  </div>
</template>

<script>

import Bot from './Bot'

export default {
  props: ['allBots'],
  data: function(){
    return {

    }
  },

  methods: {
    retireBot: function(index){
      console.log(index)
      this.allBots.splice(index,1)

    }
  },
  components: { Bot : Bot}
  
}
</script>

