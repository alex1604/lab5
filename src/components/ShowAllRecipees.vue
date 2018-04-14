<template>
<div class="awesomeRecipee" v-bind:id="name">
  <h3 class="recipeeName" v-bind:id="name">{{name}}</h3>
  <div class="recipeeDescription" v-bind:id="name">Instructions: {{description}}
  </div>
  <div class="recipeeTime" v-bind:id="name">
    <i class="far fa-clock"></i>{{preparationTime}} h
  </div>
  <div class="buttons">
    <button v-bind:id="name" v-on:click="$emit('event-mark', $event)" class="changeList" type="button" v-bind:name="name">Like
          <i class="fas fa-heart"></i>
          </button>
    <button class="showShoppingList" v-bind:name="name" v-on:click="$emit('my-event', $event)" v-bind:disabled="disableButton">What do I need?
          </button>
    <button v-on:click="changeThisStuff" type="button" v-bind:name="name" class="changeList">Change</button>
    </div>
    <div class="divChange" v-if="seen">
      <h3>Title:</h3>
      <input v-model="name" type="text">
      <h3>Instructions:</h3>
      <textarea v-model="description" name="content" rows="8" cols="40"></textarea>
    </div>
</div>
</template>

<script>
import Ingredients from "./IngredientList.vue";

export default {
  data: function() {
    return {
      seen: false,

    }
  },//data
  methods: {
    changeThisStuff: function(event) {
      this.seen = !this.seen;
      if(event.target.innerText == "Change"){
        event.target.innerText = "Save";
      }else{
        event.target.innerText = "Change";
      }
    }
  },//methods
    showShoppingList: "",

      components: {
        'ingredients-list': Ingredients,
      },
      props: ['name', 'index', 'disableButton', 'quantity', 'description', 'preparationTime', 'rightList'],

  }
</script>
<style scoped>
.buttons {
  justify-content: space-between;
}

input,
textarea {
  color: inherit;
  margin: 10px;
  width: 100%;
}

.divChange>h3 {
  margin: 5px;
  text-align: left;
}

/* .fa-heart{
      align-self: flex-end;
      display: flex;
    }
    .fa-heart:hover{
      color:#F73859;
      cursor:pointer;
      transform: scale(1.1);
    } */

.fa-clock {
  padding-right: 10px;
}

.showShoppingList {
  width: 50%;
  align-self: center;
  /* text-shadow: 1px 1px 1px black; */
  border-radius: 10px;
  padding: 10px;
  transition: all 0.3s ease;
  margin-top: 5%;
  background-color: #F1F1F1;
  border: 2px solid #0A0944;
  color: #0A0944;
  ;
  padding: 10px;
  max-width: 250px;
}

.showShoppingList:hover {
  background-color: #0A0944;
  color: #F1F1F1;
  cursor: pointer;
  box-shadow: 3px 3px 3px gray;
}

.changeList {
  width: 50%;
  border-radius: 10px;
  padding: 10px;
  transition: all 0.3s ease;
  margin-top: 5%;
  background-color: #F1F1F1;
  border: 2px solid #0A0944;
  color: #0A0944;
  ;
  padding: 10px;
  max-width: 200px;
}

.changeList:hover {
  background-color: #0A0944;
  color: #F1F1F1;
  cursor: pointer;
  box-shadow: 3px 3px 3px gray;
}

.awesomeRecipee {
  width: 80%;
  height: auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  font-family: 'Ubuntu', sans-serif;
  margin: 5%;
  padding: 4%;
  background-color: #ECECEB;
  -webkit-box-shadow: 10px 10px 43px 0px rgba(0, 0, 0, 0.53);
  -moz-box-shadow: 10px 10px 43px 0px rgba(0, 0, 0, 0.53);
  box-shadow: 10px 10px 43px 0px rgba(0, 0, 0, 0.53);
  border-radius: 5px;
}

.awesomeRecipee:hover {
  cursor: default;
}

.save {
  background-color: #0A0944;
  border: 2px solid #0A0944;
  border-radius: 10px;
  color: #F1F1F1;
  padding: 10px;
  margin-top: 5%;
  transition: all 0.3s ease;
  max-width: 200px;
  width: 50%;
}

.recipeeName {
  display: flex;
  flex-direction: row;
  justify-content: space-between;

}

.recipeeIngredients {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  /* font-family: serif !important; */
}

.eachIngredient {
  font-size: 16px;
}

.recipeeDescription {
  /* font-family: serif !important; */
  text-align: justify;
}

.recipeeTime {
  align-self: flex-end;
  justify-content: space-between;
  align-items: center;
  display: flex;

}
</style>
