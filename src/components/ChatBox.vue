<template>
  <div class="box">
    <span class="box__avatar" :style="'background-image: url(\'' + avatar + '\');'"></span>

    <div class="box__content" :class="{ 'border-less': borderLess, 'me': me }">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChatBox',
  props: {
    avatar: {
      type: String,
      required: true
    },
    borderLess: Boolean,
    me: Boolean
  }
}
</script>

<style lang="scss" scoped>
.box {
  display: flex;
  grid-gap: .5rem;
  max-width: 100%;

  &__avatar {
    width: 2rem;
    height: 2rem;
    flex: 0 0 auto;
    display: block;
    border-radius: 50%;
    background-size: cover;
    background-position: bottom;
  }

  &__content {
    width: 100%;
    overflow: hidden;
    border-radius: 1rem;
    padding: .5rem 1rem;
    background-color: #383B45;

    &.me { background-color: #DC5050 }
    &.border-less { padding: 0 }

    * { max-width: 100% }
  }
}
</style>
