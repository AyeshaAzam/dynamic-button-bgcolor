<template>
  <div>
    <div class="btn1">
      <button
        v-on="$listeners"
        :class="[dark ? 'dark' : 'light', 'baseButton']"
        class="btn"
        :style="{ backgroundColor: color }"
      >
        {{ buttonText }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "DynamicButton",

  props: {
    buttonText: {
      type: String,
      default: "label",
    },
    dark: {
      type: Boolean,
      default: false,
    },

    light: {
      type: Boolean,
      default: true,
    },
    active: {
      type: Boolean,
      default: false,
    },
    color: {
      type: String,
      default: "gray",
    },
  },
};
</script>

<style scoped>
.baseButton {
  border-radius: 5px;
  border: none;
  padding: 10px;
  width: 200px;
  height: 30px;
}

.light {
  background: white;
  color: black;
  border: 1px solid lightgray;
}

.dark {
  background: black;
  color: white;
}

.btn {
  margin: 10px;
}
</style>
