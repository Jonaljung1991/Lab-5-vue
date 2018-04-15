<template>
  <div id="app">
      <button @>Add new contact</button>
<!--    <contact-card />*-->
  </div>
</template>

<script>
    import contactCard from "./Createcontact.vue"
    export default {
        name: 'app',
        components: {
            "contact-card": contactCard
        }
    }
</script>

<!-- CSS libraries -->
<style src="normalize.css/normalize.css"></style>

<!-- Global CSS -->
<style>

</style>

<style scoped>
</style>