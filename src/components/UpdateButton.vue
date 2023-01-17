<template>
  <div class="update">
    <div class="count">
      <button class="count__btn" @click="decrement">-</button>
      <h3>{{ value }}</h3>
      <button class="count__btn" @click="increment">+</button>
    </div>
    <button @click="$emit(`add`)" class="update__btn">Update</button>
  </div>
</template>

<script>
export default {
  name: `UpdateButton`,
  data() {
    return {
      value: 0,
    };
  },
  methods: {
    decrement() {
      if (this.value) {
        this.value -= 1;
      }
    },
    increment() {
      this.value += 1;
    },
  },
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
.count {
  display: flex;
  align-items: center;
  margin-right: 15px;
  > h3 {
    padding-inline: 8px;
  }
  &__btn {
    width: 25px;
    height: 25px;
  }
}
.update {
  display: flex;
  &__btn {
    background-color: #748cdc;
    margin-right: 10px;
  }
}
</style>
