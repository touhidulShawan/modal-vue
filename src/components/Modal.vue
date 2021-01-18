<template>
  <div class="backdrop" @click.self="modalClose">
    <div class="modal">
      <h1 class="title">{{ title }}</h1>
      <p class="description">
        {{ description }}
      </p>
      <!--default slot -->
      <slot></slot>
      <div class="actions">
        <!-- named slot  -->
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "description"],
  methods: {
    modalClose() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.backdrop {
  position: fixed;
  top: 0;
  background: rgba(0, 0, 0, 0.7);
  width: 100%;
  height: 100%;
}
.modal {
  width: 400px;
  background: #f3f4f8;
  padding: 20px;
  border-radius: 10px;
  margin: 100px auto;
}
.modal h1 {
  color: rgb(5, 207, 140);
  text-align: center;
  text-transform: uppercase;
}
.modal .description {
  text-align: left;
}

.modal .actions {
  margin: 20px 0 0 0;
  height: 100%;
  width: 100%;
}
</style>