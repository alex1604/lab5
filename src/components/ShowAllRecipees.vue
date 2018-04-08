<template>
    <div class="awesomeRecipee">
        <h3 class="recipeeName">{{name}}</h3>
        <div class="recipeeDescription">Instructions: {{description}}</div>
        <div class="recipeeTime">
          <img src="../../img/clock.svg" alt="clock">
          <span>{{preparationTime}}h</span>
        </div>
        <button class="showShoppingList" v-bind:name="name" v-on:click="$emit('my-event', $event)">What you need</button>
        <div class="shoppingList" v-bind:class="{'show': showShoppingList}">
          <div class="close" v-on:click="$emit('event-hide', $event)">
            <span>x</span>
          </div>
        <div class="list">{{ingredientList}}</div>
      </div>
    </div>
</template>

<script src="../../graf/fontawesome-all.js"></script>
<script>

export default {
    showShoppingList: '',
    props: ['name', 'index', 'showShoppingList', 'currentIngredient','ingredientList', 'ingredient', 'quantity', 'description', 'preparationTime']
}

</script>
<style scoped>
    .show{
        display:flex !important;
        background-color: rgb(130, 196, 192);
        width: 50%;
        min-height: 300px;
        height: auto;
        position:fixed;
        top:30%;
        left:50%;
        transform:translate(-50%);
        z-index:3;
        flex-direction: column;
        justify-content:center;
    }

    .awesomeRecipee{
        display:flex;
        flex-direction:column;
        justify-content: flex-start;
        font-family:'Ubuntu', sans-serif;
        margin: 5%;
        padding: 4%;
        background-color: #F1F1F1;
        -webkit-box-shadow: 10px 10px 43px 0px rgba(0,0,0,0.53);
        -moz-box-shadow: 10px 10px 43px 0px rgba(0,0,0,0.53);
        box-shadow: 10px 10px 43px 0px rgba(0,0,0,0.53);
        border-radius: 5px;
    }
    .recipeeName{
        align-self:flex-start;
        color:#476269;
    }
    .recipeeIngredients{
        display:flex;
        flex-direction:row;
        justify-content: flex-start;
        font-family: serif !important;
    }
    .eachIngredient{
        font-size: 16px;
    }
    .recipeeDescription{
        font-family: serif !important;
        text-align:justify;
    }
    .recipeeTime{
        /* margin-right:3%; */
        align-self: flex-end;
        justify-content: space-around;
        align-items: center;
        display: flex;
        max-width:110px;
    }
    .recipeeTime img{
      height: 20%;
      width: 20%;

    }
    .shoppingList{
        display:none;

    }
    .showShoppingList{
      background-color:#40A798;
      border: none;
      border-radius:10px;
      color:#F1F1F1;
      cursor: help;
      padding:10px;
      max-width: 200px;
    }
    .close{
      align-self:flex-end;
      margin-right:3%;

    }
    .close span{
      font-style: normal;
      font-weight: bold;
      position: fixed;
      top: 10px;
      right: 10px;

    }
    .close:hover{
      cursor:pointer;
    }
</style>
