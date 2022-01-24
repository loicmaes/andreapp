<template>
  <div class="box">
    <img :src="avatar" alt="Avatar" class="box__thumbnail" />

    <div class="box__content">
      <p class="box__content__text">{{ text }}</p>
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
    text: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.box {

}
</style>
