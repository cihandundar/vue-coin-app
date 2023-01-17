<template>
  <div>
    <button @click="$emit(`remove`)" class="remove">Remove</button>
  </div>
</template>

<script>
export default {
  name: `RemoveButton`,
};
</script>

<style lang="scss" scoped>
button {
  border: none;
  width: 80px;
  height: 30px;
  border-radius: 6px;
  cursor: pointer;
  font-weight: bold;
  font-size: 12px;
  border: 1px solid #000;
}

.remove {
  background-color: #fe1d1a;
}
</style>
