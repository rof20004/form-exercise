<template>
  <div>
    <p>Full Name: {{ value.firstName }} {{ value.lastName }}</p>
  </div>
</template>

<script>
export default {
  props: ['value']
}
</script>

<style>
</style>