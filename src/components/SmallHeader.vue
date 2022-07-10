<template>
  <div class="small-header">
    <h3><slot></slot></h3>
  </div>
</template>

<style scoped>
.small-header {
  width: 100%;
  font-weight: bold;
  text-align: center;
  display: flex;
}
.small-header > h3 {
  display: block;
  margin: auto;
  background: #d6c18a;
  border-radius: 4px;
  padding: 0.5rem 1.5rem;
  font-size: 1.5rem;
}
</style>
