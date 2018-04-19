<template>
        <li>
             {{ingredient.quantity}} {{ingredient.name}}
        </li>
</template>
<script>

export default {
    props: ['ingredient']
}

</script>
<style scoped>
    li{
        list-style-type: square;
        text-align: left;
    }
</style>
