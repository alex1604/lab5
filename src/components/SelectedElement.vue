<template>
        <div class="marked">
            <h3>{{name}}</h3>
            <ul class="list"><ingredients-list v-for="SelectedIngredient in SelectedRecipee" v-bind:key="SelectedIngredient" v-bind:ingredient="SelectedIngredient"/></ul>
            <p>{{preparationTime}} h</p>
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
        right: -15px;
        display:flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: flex-start;
        background-color: rgb(245, 231, 154);
        border-radius: 15px;
        padding: 0 40px 0 20px;
        opacity:0.8;
    }
    .marked:hover{
        opacity:0.95;
    }
    .marked li{
        text-align: left;
    }
    .marked p{
        align-self:flex-end;
    }
</style>