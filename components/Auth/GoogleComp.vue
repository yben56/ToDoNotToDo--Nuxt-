<template>
    <button @click="$event => signIn('google')" type="button" class="btn btn-outline-dark ms-1">
        <i class="fa-brands fa-google"></i> Google
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