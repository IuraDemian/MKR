<template>
  <div id="app">
    <header>
      <nav>
        <router-link to="/">Головна</router-link>
        <router-link to="/employees">Співробітники</router-link>
        <router-link to="/about">Про фірму</router-link>
      </nav>
    </header>
    <main>
      <router-view />
    </main>
  </div>
</template>

<script>
export default 
{
  name: 'App'
};
</script>

<style src="./assets/styles.css"></style>