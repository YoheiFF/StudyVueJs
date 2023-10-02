<script setup>
import { computed, ref } from 'vue'

const count = ref(0);
const bool = ref(true);
const items = [1,2,3];
let color = ref('');
const custom_color = computed(() => {
       return color.value.toUpperCase();
    });

function increment() {
  count.value++
}
function increment2() {
  bool.value = false
}

</script>

<template>
  <button @click="increment">
    {{ count }}
  </button>
  <button @click="increment2" v-if="bool">
    条件次第で表示
  </button>

  <ul>
    <li v-for="item in items">{{item}}</li>
  </ul>
  <div :class="color">カラー</div>
  <input type="text" v-model="color">
  {{ custom_color }}
</template>

<style>
    .red{
        color:red
    }
    .green{
        color:green
    }
    .white{
        color:white
    }
</style>


<!-- <script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="huse yohei!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style> -->
