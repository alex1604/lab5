<template>
    <div class="marked">
      <div v-on:click="$emit('hide-select-el', $event)"class="close" >
        <i class="fas fa-times"></i>
      </div>
      <h3>{{name}}? Good choice!</h3>
      <ul class="list"><ingredients-list v-for="SelectedIngredient in SelectedRecipee" v-bind:key="SelectedIngredient.id" v-bind:ingredient="SelectedIngredient"/></ul>
      <p>Preparation time: {{preparationTime}} h</p>
    </div>
</template>
<script>
import Ingredients from "./IngredientList.vue";
export default {
    components:{
        "ingredients-list": Ingredients
    },
    props: ['name', 'SelectedRecipee', 'preparationTime', 'SelectedIngredient']
}

</script>
<style scoped>
    .marked{
        position: fixed;
        min-height: 200px;
        height:auto;
        max-width: 80%;
        top: 30px;
        right: 15px;
        display:flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        -webkit-box-shadow: 0px 0px 40px 0px rgba(50,77,70,1);
        -moz-box-shadow: 0px 0px 40px 0px rgba(50,77,70,1);
        box-shadow: 0px 0px 40px 0px rgba(50,77,70,1);
        background-color: #F1F1F1;
        border-radius: 5px;
        padding: 20px;
        opacity:0.95;
        /* opacity:0.8; */
    }
    .marked:hover{
        opacity:1;
        /* cursor: url("../../img/tortilla.png"); */
    }
    .marked h3{
      margin:10px;
    }
    .marked li{
        text-align: left;
    }
    .marked p, .marked div{
        align-self:flex-end;
        margin:10px;
    }

</style>
