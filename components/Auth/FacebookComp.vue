<template>
    <button @click="$event => signIn('facebook')" type="button" class="btn btn-outline-dark ms-1">
        <i class="fa-brands fa-facebook"></i> Facebook
    </button>
</template>

<script setup>
const { signIn } = useAuth()
</script>

<style scoped lang="scss">
button {
    border-color: #ccc;
}

button:focus,.btn:active {
    outline: none !important;
    box-shadow: none;
}
</style>