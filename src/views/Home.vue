<template>
  <div class="home">
    <div class="home__content">
      <ContactBox avatar="/assets/images/avatars/Ellipse-1.png" name="Jane">Hello BRO! How r u?</ContactBox>
      <ContactBox avatar="/assets/images/avatars/Ellipse-2.png" name="Jonathan">Nothing more...</ContactBox>
      <ContactBox avatar="/assets/images/avatars/Ellipse.png" name="James" @click.prevent="redirect" unread>Bro, just check this out!</ContactBox>
      <ContactBox avatar="/assets/images/avatars/Ellipse-3.png" name="Angelica">Thanks for this night <ion-icon style="color: red;" name="heart"></ion-icon></ContactBox>
      <ContactBox avatar="/assets/images/avatars/Ellipse-4.png" name="John" unread>Bro, Bowling tomorrow?</ContactBox>
      <ContactBox avatar="/assets/images/avatars/Ellipse-5.png" name="Jordan">Just check your CHAT! I'm waiting you for a long time!!!!</ContactBox>
    </div>

    <div class="home__nav">
      <p class="home__nav__link">
        <ion-icon name="home-outline"></ion-icon>
      </p>
      <p class="home__nav__link">
        <ion-icon name="search-outline"></ion-icon>
      </p>
      <p class="home__nav__link active">
        <ion-icon name="chatbubble-outline"></ion-icon>
      </p>
      <p class="home__nav__link">
        <ion-icon name="settings-outline"></ion-icon>
      </p>
      <p class="home__nav__link">
        <ion-icon name="person-outline"></ion-icon>
      </p>
    </div>
  </div>
</template>

<script>
import ContactBox from '../components/ContactBox'
export default {
  name: 'Home',
  components: { ContactBox },
  methods: {
    redirect () {
      this.$router.push('/chat/james')
    }
  }
}
</script>

<style lang="scss" scoped>
.home {
  &__content {
    display: flex;
    grid-gap: 1rem;
    padding: 1.5rem;
    flex-direction: column;
  }

  &__nav {
    left: 0;
    bottom: 0;
    width: 100%;
    display: flex;
    padding: 1rem 0;
    position: absolute;
    align-items: center;
    background-color: #1C1F29;
    justify-content: space-evenly;

    &__link {
      z-index: 2;
      display: flex;
      cursor: pointer;
      font-size: 1.5rem;
      position: relative;
      align-items: center;
      justify-content: center;

      &::before {
        top: 50%;
        left: 50%;
        opacity: 0;
        z-index: -1;
        content: '';
        width: 2.5rem;
        height: 2.5rem;
        position: absolute;
        border-radius: 50%;
        background-color: #DC5050;
        transform: translate(-50%, -50%);
      }

      &.active {
        transform: translateY(-1rem);
        &::before {
          opacity: 1;
        }
      }
    }
  }
}
</style>
