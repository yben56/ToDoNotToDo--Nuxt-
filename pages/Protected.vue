<template>
    <div class="container">
        <div class="col-sm-6 offset-sm-3">
            <div id="varifyemail" class="alert alert-warning text-center" role="alert">
                <b>This is Protect Page by middleware</b>
            </div>
        </div>
    </div>
</template>

<script setup>
definePageMeta({
    middleware: "auth"
})
</script>

<style scoped>
#varifyemail {
    margin: 250px 0;
}
</style>