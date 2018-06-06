<template>
  <div id="app">
    <header id="header">
      <h1>工事中</h1>
      <nav id="header-nav">
        <p><router-link to='/'>ホーム</router-link></p>
        <p><router-link to='/sample'>サンプルアプリ</router-link></p>
        <p><a href="https://github.com/eretica/Curriculum-Vitae" target="_blank">経歴書</a></p>
      </nav>
    </header>

    <img src="./assets/logo.svg">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
