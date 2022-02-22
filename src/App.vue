 <template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/contact">Contact</router-link>
  </div>
  <router-view v-slot="{ Component }">
    <transition name="route" mode="out-in">
      <component :is="Component"></component>
    </transition>
  </router-view>
</template>

<style>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin: 0;
  background: #f2f2f2;
}
#nav {
  padding: 30px;
}
#nav a {
  font-weight: bold;
  color: #2c3e50;
}
#nav a.router-link-exact-active {
  color: #42b983;
}

.route-enter-form {
  opacity: 0;
  transform: scale(0.2);
}
/* .route-enter-to {
  opacity: 1;
  transform: scale(1);
} */

.route-enter-active {
  transition: all 5s ease;
}
/* .route-leave-from {
  transform: translateX(200px);
} */
.route-leave-to {
  opacity: 0;
  transform: scale(0.3);
}
.route-leave-active {
  transition: all 0.3s ease-out;
}
</style>
