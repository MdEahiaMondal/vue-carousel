<template>
  <div class="slider slide-info">
    <transition name="slide">
      <slot></slot>
    </transition>
  </div>
</template>

<script>
export default {
  name: "Slider",
  setup() {},
};
</script>

<style lang="scss">
.slide-info > * {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  max-height: 100%;
  height: 100%;
  img {
    min-width: 100%;
    height: 100%;
    object-fit: cover;
  }
}
.slide-enter-active,
.slide-leave-active {
  transition: opacity 0.7s ease-in-out;
}
.slide-enter-from,
.slide-leave-to {
  opacity: 0;
}
.slide-enter-to,
.slide-leave-from {
  opacity: 1;
}
</style>
