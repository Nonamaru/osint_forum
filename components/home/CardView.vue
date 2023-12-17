<template>
<div class="card">
    card {{ num }}
</div>
</template>
<script>
export default{
    props: ['num']
}
</script>
<style scoped lang="scss">
.card{
    border: 1px solid black;
    background-color: #B6BBC4;
    padding: 8px 16px;
}
</style>