<template>
  <footer>© {{ this.date }} Topmic – All Rights Reserved</footer>
</template>

<script>
export default {
    name: 'Footer',
    data() {
        return {
            date: new Date().getFullYear()
        }
    }
}
</script>

<style scoped>
footer {
    text-align: center;
    padding: 20px;
    background: #D9665B;
    color: #ffffff;
    font-size: 16px;
    font-weight: 600;
}
</style>