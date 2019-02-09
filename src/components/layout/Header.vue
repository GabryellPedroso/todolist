<template lang="pug">
    header
        img(alt="Vue logo" src="../../assets/logo.png" width="40px")
        h1 Todo List
        div.clear
</template>
<script>
export default {
    name: 'Header'
}
</script>
<style lang="scss" scoped>
    header {
        padding: 10px 10px 5px;
        background-color: #222;
        border: 1px solid #111;
        border-top-right-radius: 5px;
        border-top-left-radius: 5px;
        img{
            float: left;
        }
        h1{
            display: block;
            color: #eee;
            float: left;
            margin-left: 15px;
        }
    }
    .clear{
        clear: left;
    }
</style>
