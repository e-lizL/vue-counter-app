<template>
  <div id="app" class="counter-app-container">
    <h1 class="counter-heading">Counter</h1>
    <p id="counter">{{ counter }}</p>
    <div class="button-container">
      <button @click="increment" id="increase">Increment</button>
      <button @click="reset">Reset</button>
      <button @click="decrement" id="decrement">Decrement</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Vue Counter App",
  data() {
    return {
      counter: 0,
    };
  },
  methods: {
    increment() {
      this.counter++;
    },
    decrement() {
      this.counter--;
    },
    reset() {
      this.counter = 0;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.counter-app-container {
  width: 100%;
  height: 100vh;
  background-color: #45036a;
  background-image: linear-gradient(160deg, #45036a 0%, #cebce4 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  font-family: "Poppins", sans-serif;
  flex-direction: column;
}

.counter-heading {
  font-size: 4rem;
  letter-spacing: 1.2px;
}

#counter {
  font-size: 3rem;
  margin: 35px 0;
}

.button-container {
  width: 100%;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

button {
  font-size: 30px;
  padding: 20px 40px;
  color: #fff;
  border: 1px solid #fff;
  cursor: pointer;
  background: #44d7d5;
  position: relative;
  border-radius: 8px;
  overflow: hidden;
  margin: auto;
}

button::before {
  content: "";
  width: 200px;
  height: 40px;
  background-color: rgba(255, 255, 255, 0.2);
  position: absolute;
  top: 0;
  left: -180px;
  transform: rotate(45deg);
  transition: 0.3s;
}

button:not(:last-child) {
  margin-right: 25px;
}

button:hover {
  background-color: rgba(6, 11, 121, 0.484);
}

button:hover::before {
  left: 250px;
}

/* Media Queries */
@media (max-width: 684px) {
  .button-container {
    flex-direction: column;
  }
  button:not(:last-child) {
    margin: 25px auto;
  }
  #increase {
    margin-left: auto;
  }
}

@media (max-width: 364px) {
  button {
    font-size: 20px;
    padding: 15px 30px;
  }
  .counter-heading {
    font-size: 40px;
  }
  #counter {
    font-size: 65px;
  }
}
</style>
