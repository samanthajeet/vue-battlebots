<template>
  <div class='botcard'>
    <h5>{{botObj.botName}}</h5>
    <p>Attack: {{botObj.attackVal}}</p>
    <p>Health: {{botObj.healthVal}}</p>
    <section class='bot-btns'>
      <button @click='onSelect(botObj)' class='botbtn'> select </button>
      <button @click='retireBot(index)' class='botbtn'> retire </button>
    </section>

  </div>
</template>

<script>
export default {
  props: ['botObj', 'retireBot', 'index', 'onSelect']
  
}
</script>



