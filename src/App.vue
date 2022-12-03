<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Dynamic Button Component" />

    <DynamicButton
      buttonText="Dark Mode"
      :dark="true"
      @click="handleDarkMode"
      :color="active ? 'red' : 'blue'"
    />
    <!-- default is the light mode so we dont have to pass any pops to it-->
    <DynamicButton
      buttonText="Light Mode"
      @click="handleLightMode"
      :color="active ? this.color : '#16a085'"
    />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import DynamicButton from "./components/DynamicButton.vue";

/**************************************************************************************
 * Watch: Vue.js - Dynamic & Reusable Button Component In Vue.js
 * https://www.youtube.com/watch?v=2Evw5h_1Ko8
 *
 * Render class bases on PROPS , dynamic class on button by binding class and pass an array
 *
 * Using the $listeners property, you can forward all event listeners on
 * the component to a specific child element with v-on="$listeners"
 *
 * check issues I had : https://stackoverflow.com/questions/74643295/button-background-color-doesnot-changes-when-clicked-on-it/74643605?noredirect=1#comment131784986_74643605
 ***************************************************************************************/

export default {
  name: "App",
  components: {
    HelloWorld,
    DynamicButton,
  },

  props: {
    // darkColorChange: {
    //   type: String,
    //   default: "",
    // },
    // lightColorChange: {
    //   type: String,
    //   default: "",
    // },
  },

  data() {
    return {
      active: true,
      color: "#3aa1b6",
    };
  },

  methods: {
    handleDarkMode() {
      console.log("Dark-mode clicked");
      // eslint-disable-next-line
      // this.darkColorChange.style.backgroundColor = "pink";
      this.active = !this.active;
    },

    handleLightMode() {
      console.log("Light-mode clicked");
      this.active = !this.active;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
