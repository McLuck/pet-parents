<template>
  <textarea :placeholder="placeholder" v-model="inputValue" class="textarea" />
</template>

<script>
export default {
  name: 'Textarea',
  props: {
    placeholder: {
      type: String,
      default: '',
    },
    value: {
      type: String,
      default: '',
    },
  },
  watch: {
    value(val) {
      this.inputValue = val;
    },
  },
  data: () => ({
    inputValue: '',
  }),
};
</script>

<style lang="scss">
@import '../../utils/scss/index.scss';

.textarea {
  height: 35px;
  border: 1px solid rgba($color: #000000, $alpha: 0.16);
  font-size: var(--font-size-default);
  padding: var(--space-sm);
  height: 114px;
  max-height: 114px;
  @include border-radius(light);

  &:hover {
    border-color: var(--color-text-dark);
  }

  &:focus {
    border-color: var(--color-primary);
  }

  &::placeholder {
    color: var(--color-text-gray);
  }
}
</style>
