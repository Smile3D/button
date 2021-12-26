<template>
  <button
    class="btn"
    :style="options"
    :type="type"
    :disabled="disabled"
    @mouseover="changeColor"
    @mouseleave="originalColor"
    @click="onHandler"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "GeneralButton",
  props: {
    type: String,
    customBackgroundColor: String,
    customColor: String,
    hoverBackgroundColor: String,
    hoverColor: String,
    borderRadius: String,
    border: String,
    minHeight: String,
    minWidth: String,
    disabled: Boolean,
    fontSize: String,
    fontWeight: String
  },
  data() {
    return {
      options: {
        backgroundColor: this.customBackgroundColor,
        color: this.customColor,
        borderRadius: this.borderRadius,
        minWidth: this.minWidth,
        minHeight: this.minHeight,
        fontSize: this.fontSize,
        fontWeight: this.fontWeight,
        border: this.border,
        transition: 'all .3s'
      }
    }
  },
  methods: {
    originalColor() {
      return (
        this.options.backgroundColor = this.customBackgroundColor,
        this.options.color = this.customColor
      )
    },
    changeColor() {
      return (
        this.options.backgroundColor = this.hoverBackgroundColor,
        this.options.color = this.hoverColor
      )
    },
    onHandler() {
      this.$emit('onClick')
    }
  }
}
</script>

<style scoped lang="scss">
  .btn {
    display: inline-grid;
    justify-content: center;
    padding: 10px 15px;
    align-items: center;
    outline: none;
    border: none;
    cursor: pointer;
  }
</style>
