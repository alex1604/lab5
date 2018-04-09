<template>
    <div class="awesomeRecipee" v-on:click="$emit('event-mark', $event)" v-bind:id="name">
        <h3 class="recipeeName"  v-on:click="$emit('event-mark', $event)" v-bind:id="name">{{name}}</h3>
        <div class="recipeeDescription" v-on:click="$emit('event-mark', $event)" v-bind:id="name">Instructions: {{description}}</div>
        <div class="recipeeTime" v-on:click="$emit('event-mark', $event)" v-bind:id="name">
          <i class="far fa-clock"></i>{{preparationTime}}h</div>
        <button class="showShoppingList" v-bind:name="name" v-on:click="$emit('my-event', $event)" v-bind:disabled="disableButton">What do I need?</button>
    </div>
</template>

<script>
import Ingredients from "./IngredientList.vue"
export default {
    showShoppingList: '',
    components: {
        'ingredients-list' : Ingredients
    },
    props: ['name', 'index', 'disableButton', 'quantity', 'description', 'preparationTime', 'rightList']
}

</script>
<style scoped>

    .fa-edit:hover{
        cursor:pointer;
        transform: scale(1.1);
    }
    .showShoppingList{
        width:40%;
        align-self:center;
        text-shadow: 1px 1px 1px black;
        border-radius: 10px;
        padding: 10px;
        transition: all 0.5s ease;
        margin-top: 5%;
        background-color:#40A798;
        border: none;
        color:#F1F1F1;
        padding:10px;
        max-width: 200px;

    }
    .showShoppingList:hover{
        cursor:pointer;
        box-shadow: 3px 3px 3px gray;

    }

    .awesomeRecipee{
        width:70%;
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

    .awesomeRecipee:hover{
        cursor:pointer;
    }
    .recipeeName{
        display:flex;
        flex-direction: row;
        justify-content: space-between;

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


</style>
