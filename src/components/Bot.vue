<template>
  <div>
    <h2>{{botObj.botName}}</h2>
    <p>Attack: {{botObj.attackVal}}</p>
    <p>Health: {{botObj.healthVal}}</p>
    <button @click='onSelect(botObj)'> SELECT </button>
    <button @click='retireBot(index)'> RETIRE</button>
    <hr>
  </div>
</template>

<script>
export default {
  props: ['botObj', 'retireBot', 'index', 'onSelect']
  
}
</script>

