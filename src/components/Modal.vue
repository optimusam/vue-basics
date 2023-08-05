<template>
  <div class="modal" :class="{'is-active': showModal}">
    <div class="modal-background"></div>
    <div class="modal-card">
      <header class="modal-card-head">
        <p class="modal-card-title">{{ title }}</p>
        <button class="delete" aria-label="close" @click="closeModal"></button>
      </header>
      <section class="modal-card-body">
        {{ content }}
        <slot></slot>
      </section>
      <footer class="modal-card-foot">
        <button class="button is-success">Save changes</button>
        <button class="button" @click="closeModal">Cancel</button>
      </footer>
    </div>
  </div>

</template>

<script>
export default {
    props: {
        title: String,
        content: String,
        showModal: Boolean
    },
    methods: {
      closeModal() {
        this.$emit('close');
      }
    }
}
</script>