<template>
    <div class="awesomeRecipee"  v-bind:id="name">
        <h3   v-on:click="$emit('event-mark', $event)" class="recipeeName"  v-bind:id="name">{{name}}</h3>
        <div  v-on:click="$emit('event-mark', $event)" class="recipeeDescription"
        v-bind:id="name">Instructions: {{description}}
        </div>
        <div class="recipeeTime"
         v-bind:id="name">
          <i class="far fa-clock"></i>{{preparationTime}} h
        </div>

        <!-- v-on:click="$emit('event-mark', $event)" -->
        <!-- <div v-bind:id="name" >
          <i v-bind:id="name" class="fas fa-heart fa-2x"></i>
        </div> -->
        <div class="buttons">
          <button class="showShoppingList" v-bind:name="name" v-on:click="$emit('my-event', $event)" v-bind:disabled="disableButton">What do I need?</button>
          <button v-on:click="changeThisStuff" type="button" v-bind:name="name" class="changeList">Change</button>
        </div>
        <div v-if="seen">
          <input v-model="name" type="text" name="changeTitle">
          <textarea v-model="description" name="content" rows="8" cols="40"></textarea>
          <input type="text" name="changeTitle" v-model="preparationTime">
        </div>

    </div>
</template>

<script>
import Ingredients from "./IngredientList.vue";

export default {
  data: function(){
    return{
      seen: false
    }
  },
  methods:{
    changeThisStuff: function(event){
      this.seen = !this.seen;
      if(event.target.innerText !== "Save"){
        event.target.innerText = "Save";
      }else{
        event.target.innerText = "Change";
      }
    },

  },
    showShoppingList: "",

    components: {
        'ingredients-list' : Ingredients
    },
    props: ['name', 'index', 'disableButton', 'quantity', 'description', 'preparationTime', 'rightList'],

}

</script>
<style scoped>

  .buttons{
    justify-content: space-between;
  }
  input, textarea{
    color: inherit;
    margin:10px;
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
        width:50%;
        align-self:center;
        /* text-shadow: 1px 1px 1px black; */
        border-radius: 10px;
        padding: 10px;
        transition: all 0.3s ease;
        margin-top: 5%;
        background-color:#F1F1F1;
        border: 2px solid  #0A0944;;
        color: #0A0944;;
        padding:10px;
        max-width: 250px;
    }
    .showShoppingList:hover{
        cursor:pointer;
        box-shadow: 3px 3px 3px gray;
    }
    .changeList{
        width:50%;
        border-radius: 10px;
        padding: 10px;
        transition: all 0.3s ease;
        margin-top: 5%;
        background-color:#F1F1F1;
        border: 2px solid  #0A0944;;
        color: #0A0944;;
        padding:10px;
        max-width: 200px;
}
.changeList:hover{
    cursor:pointer;
    box-shadow: 3px 3px 3px gray;
}
    .awesomeRecipee{
        width: 80%;
        height: auto;
        display:flex;
        flex-direction:column;
        justify-content: center;
        font-family:'Ubuntu', sans-serif;
        margin: 5%;
        padding: 4%;
        background-color: #FBE4C9;
        -webkit-box-shadow: 10px 10px 43px 0px rgba(0,0,0,0.53);
        -moz-box-shadow: 10px 10px 43px 0px rgba(0,0,0,0.53);
        box-shadow: 10px 10px 43px 0px rgba(0,0,0,0.53);
        border-radius: 5px;
    }
    .awesomeRecipee:hover{
      cursor: default;
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
