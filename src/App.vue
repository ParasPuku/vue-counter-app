<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125"
    />

    <div class="wrapper">
      <h1>Counter Application</h1>
    </div>
    <div class="counter-wrapper">
      <h2 class="counter-value">
        {{ this.count < 10 ? `0${this.count}` : this.count }}
      </h2>
    </div>
    <div class="buttons">
      <button class="prev-btn" v-on:click="decrementValue">Prev</button>
      <button class="reset-btn" v-on:click="resetValue">Reset</button>
      <button class="next-btn" v-on:click="incrementValue">Next</button>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
    };
  },
  methods: {
    incrementValue() {
      this.count = this.count + 1;
    },
    decrementValue() {
      this.count = this.count > 0 ? this.count - 1 : 0;
    },
    resetValue() {
      this.count = 0;
    },
  },
};
</script>

<style>
@import "./assets/base.css";
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');

#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}

.wrapper h1 {
    font-family: Montserrat;
    font-size: 34px;
}

header {
  line-height: 1.5;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

/* .logo {
  display: block;
  margin: 0 auto 2rem;
} */

a,
.green {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}

button {
    font-size: 30px;
    letter-spacing: 2px;
    padding: 5px 10px;
    margin: 0 5px;
    background-color: #cacaca;
    border: 2px solid #ff5050;
    cursor: pointer;
    border-radius: 10px 0 10px 0;
    font-family: Montserrat;
}

h2.counter-value {
    font-size: 200px;
    font-family: Montserratw;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

@media (min-width: 1024px) {
  body {
    display: flex;
    place-items: center;
  }

  /* #app {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 0 2rem;
  } */

  /* header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  } */

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  /* .logo {
    margin: 0 2rem 0 0;
  } */
}
</style>
