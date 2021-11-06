<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="..\images\logo.png">
      </router-link>
    </div>
    <div id="side">
      <router-link to="/genre">
        <div class="menu-item genre">
          <p>Search by genre</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
  <div class="footer">
    <a href="https://github.com/BriK1330/Creative-Project-3">Github- Briana</a>
  </div>
</div>
</template>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;

}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
}

#menu a {
  color: #B84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: right;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.genre {
  margin-right: 50px;
}
.footer {
  text: #79a668;
  float: right;
  text-align: right;
}
</style>
