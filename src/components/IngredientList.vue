<template>
        <li>
            {{ingredient.name}}, {{ingredient.quantity}}
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