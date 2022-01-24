<template>
  <div class="box">
    <img :src="avatar" alt="Avatar" class="box__thumbnail" />

    <div class="box__content">
      <h1 class="box__content__name">{{ name }}</h1>
      <p class="box__content__message" :class="{ new: unread }"><slot></slot></p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ContactBox',
  props: {
    avatar: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    unread: Boolean
  }
}
</script>

<style lang="scss" scoped>
.box {
  width: 100%;
  display: flex;
  cursor: pointer;
  grid-gap: 1.5rem;
  align-items: center;
  transition: transform 250ms ease;
  * { user-select: none }

  &:hover {
    transform: translateX(1rem);
  }

  &__thumbnail {
    width: 2rem;
  }

  &__content {
    width: 100%;
    display: flex;
    overflow: hidden;
    flex-direction: column;

    &__name {
      font-weight: 600;
      font-size: 1.5rem;
    }

    &__message {
      opacity: .4;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
      &.new { font-weight: 600 }
    }
  }
}
</style>
