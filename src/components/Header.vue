<template>
  <nav class="nav">
    <div class>
      <img :src="require('@/assets/logo.png')">
    </div>
    <div>
      <h1>Ejericio Vue3</h1>
      <h2>Master contínuo</h2>
    </div>
  </nav>
</template>

<style lang="scss">
  .nav {
    display: flex;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-content: center;
    align-items: center;
    padding: 20px;
    margin-bottom: 20px;
    border-bottom: 1px solid yellowgreen;
  }
</style>