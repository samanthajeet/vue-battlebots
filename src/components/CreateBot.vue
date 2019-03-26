<template>
  <div>
    <h1>create bot component</h1>
    <div>
      <p>Bot Name</p>
      <input type="text" v-model='botName'>
    </div>
    <div>
      <p>Attack Value</p>
      <input type="text" v-model='attackVal'>
    </div>
    <div>
      <p>Health Value</p>
      <input type="text" v-model='healthVal'>
    </div>
    <button @click='createBot' >create bot</button>
  </div>
</template>


<script>
export default {
  props: ['allBots','addBot'],
  data: function(){
    return {
      botName: '',
      attackVal: '',
      healthVal: ''
    }
  },
  methods: {
    createBot: function(){
      const newBot = { botName: this.botName, attackVal: this.attackVal, healthVal: this.healthVal}
      this.addBot(newBot)
    }
  }
  
}
</script>
