<template>
  <div id="app">
    <div class="header">
      <button @click="toggleCreate">toggle</button>
      <h1>Bob's Battle Bots</h1>
      <button @click="toggleCreate">toggle</button>
    </div>
    <section v-if="!showBots" class="createbots">
      <create-bot :allBots="allBots" :addBot="addBot"/>
    </section>
    <section v-else>
      <bot-list :allBots="allBots"/>
    </section>
  </div>
</template>

<script>
import CreateBot from "./components/CreateBot";
import BotList from "./components/BotList";

export default {
  name: "app",
  data: function() {
    return {
      showBots: false,
      allBots: []
    };
  },
  methods: {
    toggleCreate: function() {
      this.showBots = !this.showBots;
    },
    addBot: function(bot) {
      this.allBots.push(bot);
      this.toggleCreate();
    }
  },
  components: { "create-bot": CreateBot, "bot-list": BotList }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Permanent+Marker');

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  box-sizing: border-box;
  height: 100vh;
}

.header {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}

.header h1{
  font-family: 'Permanent Marker', cursive;
  font-size: 4rem;
  letter-spacing: 0.25rem;
  color: #404244
}

.header button {
  width: 10%;
  height: 1.75rem;
  background: #404244;
  color: white;
  border: none;
}

.createbots {
  margin-top: 2rem;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  align-content: center;
}

.createbot-card {
  padding: 1rem;
  width: 25%;
  height: 25rem;
  border: 2px solid #404244;
  box-shadow: 1px 1px 5px grey;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-content: center;
  align-items: center;
}

.createbot-card input {
  width: 17rem;
  height: 2rem;
  padding: 0.5rem;
  outline: 1px solid #404244;
}

input:focus {
    outline: none;
    border: 1px solid #09f9f1;
}
.createbot-card button {
  width: 50%;
  height: 1.75rem;
  background: #404244;
  color: white;
  border: none;
}

.botlist h4{
  font-family: 'Permanent Marker', cursive;
  font-size: 2rem;
  color: #404244
}

.bot1{
  color: #09f9f1;
  text-shadow: 2px 2px 3px #404244;
  font-size: 2.5rem;
  letter-spacing: 0.1rem;
}

.bot2{
  color: #f909d0;
  text-shadow: 2px 2px 2px #404244;
  font-size: 2.5rem;
  letter-spacing: 0.1rem;
}

.botlistbtn {
  width: 10%;
  height: 1.75rem;
  background: #404244;
  color: white;
  border: none;
  margin: 1rem;
}

.bots {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;

}
.botcard {
  padding: 1rem;
  margin: 1rem;
  width: 20%;
  border: 2px solid #404244;
  box-shadow: 1px 1px 5px grey;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-content: center;
  align-items: center;
}

.botcard h5{
  font-family: 'Permanent Marker', cursive;
  font-size: 2rem;
  color: #404244;
  margin: 0;
}

.bot-btns {
  display: flex;
  justify-content: space-around;
  
}

.botbtn {
  width: 4rem;
  height: 1.75rem;
  background: #404244;
  color: white;
  border: none;
  margin: 0.75rem;
}

</style>
