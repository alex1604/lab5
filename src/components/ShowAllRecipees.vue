<template>
    <div class="awesomeRecipee"  v-bind:id="name">
        <h3  class="recipeeName"  v-bind:id="name">{{name}}</h3>
        <div class="recipeeDescription"
        v-bind:id="name">Instructions: {{description}}
        </div>
        <div class="recipeeTime"
         v-bind:id="name">
          <i class="far fa-clock"></i>{{preparationTime}}h
        </div>
        <div v-bind:id="name" v-on:click="$emit('event-mark', $event)">
          <i v-bind:id="name" class="fas fa-heart fa-2x"></i>
        </div>
        <div class="buttons">
          <button class="showShoppingList" v-bind:name="name" v-on:click="$emit('my-event', $event)" v-bind:disabled="disableButton">What do I need?</button>
          <button v-on:click="$emit('change-to-input', $event)" type="button" name="button" class="changeList">Change</button>
        </div>
        <form v-if="toggleInput" >
          <h3>Change Title or Instructions</h3>
          <label for="title">Title</label>
          <input name="title" v-model:value="name" v-bind:placeholder="name" type="text" >
          <label for="content">Instructions</label>
          <textarea v-model:value="description" name="content" rows="8" cols="40"></textarea>
      </form>
    </div>
</template>

<script>
import Ingredients from "./IngredientList.vue";

export default {

    showShoppingList: "",

    components: {
        'ingredients-list' : Ingredients
    },
    props: ['name', 'index', 'disableButton', 'quantity', 'description', 'preparationTime', 'rightList', 'toggleInput'],

}

</script>
<style scoped>

  .buttons{
    justify-content: space-between;
  }
  label{
    display: flex;
    align-self: flex-start;

  }
  input, textarea{
    width: 100%;
  }
    .fa-heart{
      align-self: flex-end;
      display: flex;
    }
    .fa-heart:hover{
      color:#F73859;
      cursor:pointer;
      transform: scale(1.1);
    }
    .fa-clock{
      padding-right: 10px;
    }
    .showShoppingList{
        width:40%;
        align-self:center;
        /* text-shadow: 1px 1px 1px black; */
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
    .changeList{
        width:40%;
        border-radius: 10px;
        padding: 10px;
        transition: all 0.5s ease;
        margin-top: 5%;
        border: 2px solid #40A798;
        background-color: none;
        color:#40A798;;
        padding:10px;
        max-width: 200px;
}
.changeList:hover{
    cursor:pointer;
    box-shadow: 3px 3px 3px gray;
}
    .awesomeRecipee{
        min-width: 70%;
        height: auto;
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

    .recipeeName:hover{
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
        /* font-family: serif !important; */
    }
    .eachIngredient{
        font-size: 16px;
    }
    .recipeeDescription{
        /* font-family: serif !important; */
        text-align:justify;
    }
    .recipeeTime{
        align-self: flex-end;
        justify-content: space-between;
        align-items: center;
        display: flex;

    }



</style>
