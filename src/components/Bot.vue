<template>
  <div class='botcard'>
    <h2>{{botObj.botName}}</h2>
    <p>Attack: {{botObj.attackVal}}</p>
    <p>Health: {{botObj.healthVal}}</p>
    <section class='bot-btns'>
      <button @click='onSelect(botObj)'> SELECT </button>
      <button @click='retireBot(index)'> RETIRE</button>
    </section>

  </div>
</template>

<script>
export default {
  props: ['botObj', 'retireBot', 'index', 'onSelect']
  
}
</script>



