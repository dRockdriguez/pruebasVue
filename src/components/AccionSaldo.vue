<template>
  <div>
    <button @click="emitAction" :disabled="disabled">{{ text }}</button>
  </div>
</template>

<script>
export default {
    name: 'accion-saldo',
    props: {
        text: String,
        disabled: {
            type: Boolean,
            default: false
        }
    },
    methods: {
        emitAction() {
            this.$emit('action');
        }
    }
}
</script>

<style scoped>
    div {
        margin-top: 10px;
    }
</style>