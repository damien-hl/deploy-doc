<template>
  <p class="alert">
    {{ message }}
  </p>
</template>

<script>
  export default {
    props: {
      message: String
    }
  }
</script>

<style scoped>
.alert {
  padding: 0.75rem 1rem;
  background: #FFF5F5;
  border: 1px solid #C53030;
  border-radius: 0.25rem;
  font-size: .875rem;
  font-weight: 700;
  color: #C53030;
}
</style>
