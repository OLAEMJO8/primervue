<template>
  <div>
    <header>
      <div>
        <nav>
          <RouterLink to="/" class="nav-link">Ciclo</RouterLink>
          <RouterLink to="/about" class="nav-link">Methods</RouterLink>
        </nav>
      </div>
    </header>
    <div class="content">
      <RouterView />
    </div>
  </div>
</template>

<style scoped>


nav {
  display: flex;
  justify-content: center;
  padding: 0 24px;
  text-align: center;
  padding: 10px 20px;
  background-color: #9d8cb1;
}

.nav-link {
  text-decoration: none;
  color: #ffffff;
  margin: 0 10px;
  padding: 10px 20px;
  font-family:Verdana, Geneva, Tahoma, sans-serif;
  background-color: #45236b;
font-size: 12px;
border: none;
border-radius: 5px;
cursor: pointer;
}

.content {
  font-family:Verdana, Geneva, Tahoma, sans-serif;
  font-size: 12px;
  display: center;
  flex-direction: column;
  align-items: center;
  margin-top: 2rem;
  color: #000;
  

}
</style>
