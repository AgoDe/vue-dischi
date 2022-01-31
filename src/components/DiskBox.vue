<template>

    <div class="disk-box">
        <img :src="disk.poster" :alt="disk.title">

        <h3 class="title"> {{disk.title}} </h3>
        <div class="details artist"> {{disk.author}} </div>
        <div class="details year"> {{disk.year}} </div>
    </div>

</template>

<script>
export default {
    props: {
        disk: Object,
    }
    
}
</script>

<style lang="scss" scoped>

    .disk-box {
        width: 130px;
        padding: 10px;
        margin: 10px;
        background: rgb(53, 61, 71);
        color: white;
        text-align: center;

        img {
            width: 110px;
            height: 110px;
            object-fit: cover;
        }
        .title {
            font-size: 13px;
            padding: 4px;
            text-transform: uppercase;
        }
        .details {
            color:#888;
            font-size: 10px;
            padding: 2px;
        }
        
    }

</style>