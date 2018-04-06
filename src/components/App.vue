<template>
  <div id="app">
    <div class="banner">
      <img
        src="../../img/tortilla.png"
        width="300"
        alt="vue"
        class="logo"
      />
      <h1>Welcome to iFood</h1>
    </div>
    <div class="bottom">
      To get started, edit <code>./src/components/App.vue</code> and save to reload.<br/>
      <span class="fade">
        Checkout <code>./README.md</code> for more usages.
      </span>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'app'
  }

  /************************************
  RECIPEE OBJEKT:
  {
    name: 'spanish tortilla',
    ingredienser: [
      {
        'name': 'potato'
        'quantity' : '1kg'
      },
      {
        'name': 'egg'
        'quantity' : '8'
      },
      {
        'name': 'olive oil'
        'quantity' : '3dl'
      },
      {
        'name': 'salt'
        'quantity' : '5g'
      }
    ],
    description: '',
    preparationTime: ''
  }
  */

</script>

<!-- CSS libraries -->
<style src="normalize.css/normalize.css"></style>

<!-- Global CSS -->
<style>
  code {
    font-family: Menlo, Monaco, Lucida Console, Liberation Mono, DejaVu Sans Mono, Bitstream Vera Sans Mono, Courier New, monospace, serif;
    font-size: 0.9em;
    white-space: pre-wrap;
    color: #2c3e50;
  }

  code::before, code::after {
    content: '`';
  }
</style>

<!-- Scoped component css -->
<!-- It only affect current component -->
<style scoped>
  #app {
    text-align: center;
  }

  #app h1 {
    color: #2c3e50;
    font-weight: 300;
    margin: 0;
  }

  .banner {
    height: 200px;
    background-color: #f6f6f6;
    padding: 50px 10px;
  }

  .bottom {
    padding: 80px 10px;
    font-size: 24px;
    font-weight: 300;
  }

  .fade {
    font-size: 14px;
  }

  .logo {
    animation: spin 6s 1s infinite linear
  }

  @keyframes spin {
    from {transform:rotate(0deg);}
    to {transform:rotate(360deg);}
  }
</style>
