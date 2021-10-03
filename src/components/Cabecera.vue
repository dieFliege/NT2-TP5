<template>
    <header>
        <img alt="Logo de Vue" src="../assets/logo.png" height="50">
        <p>{{ titulo }}</p>
    </header>
</template>

<script>
    export default {
        name: 'Cabecera',
        props: ['titulo']
    }
</script>

<style>
    header {
        display: flex;
        border-bottom: 1px solid #ccc;
        padding: .5rem 1rem;
    }
    ul {
        list-style: none;
    }
</style>