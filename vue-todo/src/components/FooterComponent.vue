<template>
    <div>
      <button v-on:click="removeItemAll">RemoveItemAll</button>
    </div>
</template>
<script>
export default {
    methods: {
        removeItemAll: function() {
            this.$emit("removeItemAll");
        }
    }
}
</script>
<style scoped>

</style>
