<template>
    <button @click="$event => signIn('github')" type="button" class="btn btn-outline-dark">
        <i class="fa-brands fa-github"></i> GitHub
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