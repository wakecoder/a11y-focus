<template>
  <div tabindex="1" ref="a11yDiv">
    <slot></slot>
  </div>
</template>
<script>
export default {
  mounted() {
    const self = this
    this.$router.afterEach(() => {
      if (self.route) {
        self.$refs.a11yDiv.focus()
      }
    });
  },
  updated() {
    if (this.data) {
      this.$refs.a11yDiv.focus()
    }
  },
  props: {
    data: {
      type: Boolean,
      default: true
    },
    route: {
      type: Boolean,
      default: false
    }
  }
}
</script>
