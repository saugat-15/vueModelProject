<template>
  <div class="backdrop" ref="backdrop" @click.self="closeModel">
    <div class="model" :class="{ sale: theme === 'sale' }">
      <!-- <i class="fa fa-times" aria-hidden="true" @click="handleHide"></i> -->
        <slot></slot>
        <div class="action">
            <slot name="links"></slot>
        </div>
        <div class="action">
            <slot name="secondLink"></slot>
        </div>
      <!-- <h1>{{ header }}</h1>
      <p>{{ text }}</p> -->
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

.model .action{
    text-align: center;
    margin: 30px 0 10px 0;
}

.model .action a {
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}

.model.sale {
  background: crimson;
  color: #fff;
}

.model.sale h1 {
  color: white;
}

.model.sale.action {
    color: white;
}
.model.sale.action a{
    color: #fff;
}
</style>
