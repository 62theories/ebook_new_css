<template>
  <a
    :href="$to"
    :class="
      `homepage-navbar-item ${
        $route.path === $to ? 'homepage-navbar-item-active' : ''
      }`
    "
  >
    <slot></slot>
  </a>
</template>

<script>
export default {
  props: {
    to: String
  }
};
</script>
