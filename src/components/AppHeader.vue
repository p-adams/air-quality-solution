<template>
  <header>
    <img alt="Generic company logo" src="../assets/generic-company-logo.png" />
    <nav>
      <ul class="navigation">
        <li><a href="#/">Link</a></li>
        <li><a href="#/">Link</a></li>
      </ul>
    </nav>
  </header>
</template>
export default {}
<style scoped>
header {
  max-width: 1440px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px;
}

.navigation {
  display: flex;
  list-style: none;
}
.navigation > li > a {
  text-decoration: none;
  padding: 5px;
  color: black;
}
</style>
