<template>
  <div class="backdrop" ref="backdrop" @click="closeModel">
    <div class="model" :class="{ sale: theme === 'sale' }">
      <!-- <i class="fa fa-times" aria-hidden="true" @click="handleHide"></i> -->

      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "text", "theme"],
  methods: {
      closeModel() {
        this.$emit('close')
    },
  },
};
</script>

<style>
.model {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: #fff;
  border-radius: 10px;
}

.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

.model h1 {
  color: rgb(15, 226, 163);
  border-style: none;
  padding: 0;
}

.model i {
  display: flex;
  justify-content: flex-end;
  cursor: pointer;
}

.model.sale {
  background: crimson;
  color: #fff;
}

.model.sale h1 {
  color: white;
}
</style>
