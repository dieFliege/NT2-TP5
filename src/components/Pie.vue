<template>
    <footer>
        <p>{{ autor }} &copy; {{ new Date().getFullYear() }}</p>
    </footer>
</template>

<script>
    export default {
        name: 'Pie',
        props: ['autor']
    }
</script>