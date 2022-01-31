<template>
    
    <main>

        <div class="flex-box">

            <disk-box 
            v-for="(disk, index) in disks"
            :key="index"
            :disk="disk"
            />

        </div>

    </main>

</template>

<script>
import DiskBox from './DiskBox.vue'

export default {
  components: { 
      DiskBox, },
    props: {
        disks: Array,
    }
    
}
</script>

<style lang="scss" scoped>

    main {
        padding: 30px;
        background: rgb(40, 49, 61);

        .flex-box {
            display: flex;
            flex-wrap: wrap;
    
            width: 750px;
            margin: 0 auto;
        }
    }

</style>