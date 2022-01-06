<template>
  <ul>
    <li><button type="button" :class="{active: activeOption === 'poor'}" @click="activate('poor')">Poor</button></li>
    <li><button type="button" :class="{active: activeOption === 'average'}" @click="activate('average')">Average</button></li>
    <li><button type="button" :class="{active: activeOption === 'great'}" @click="activate('great')">Great</button></li>
  </ul>
</template>

<script>
export default {
  props: ['modelValue'],
  emits: ['update:modelValue'],
  data() {
    return {
      activeOption: null, 
    }
  },
  methods: {
    activate(option) {
      this.activeOption = option
      this.$emit('update:modelValue', option)
    }
  }
}
</script>

<style scoped>
ul {
  list-style: none;
  display: flex;
  flex-direction: row;
}
button {
  padding: 20px;
  margin-left: 5px;
}
.active {
  border-color: red;
}
button.active {
  background-color: red;
}
</style>