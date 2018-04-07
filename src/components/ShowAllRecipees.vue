<template>
    <div class="awesomeRecipee">
        <h3 class="recipeeName">{{name}}</h3>
        <div class="recipeeDescription">Instructions: {{description}}</div>
        <div class="recipeeTime">{{preparationTime}}h</div>
        <button class="showShoppingList" v-bind:name="name" v-on:click="$emit('my-event', $event)">What you need</button>
        <div class="shoppingList" v-bind:class="{'show': showShoppingList}"><div class="close" v-on:click="$emit('event-hide', $event)"><i class="fas fa-times">X</i></div><div class="list">{{ingredientList}}</div></div>
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
        position:absolute;
        top:50%;
        left:50%;
        transform:translate(-50%);
        z-index:3;
        flex-direction: column;
        justify-content:space-around;
    }
    .awesomeRecipee{
        display:flex;
        flex-direction:column;
        justify-content: flex-start;
        font-family:'Ubuntu', sans-serif;
        margin: 5%;
    }
    .recipeeName{
        align-self:flex-start;
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
        margin-right:3%;
        align-self: flex-end;
    }
    .shoppingList{
        display:none;
    }
    .close{
        align-self:flex-end;
        margin-right:3%;
    }
    .close:hover{
        cursor:pointer;
    }
</style>
