<template>
  <div class="chat">
    <header class="chat__header">
      <router-link to="/" class="chat__header__back"><ion-icon name="return-down-back-outline"></ion-icon></router-link>
      <img src="/assets/images/avatars/Ellipse.png" alt="James Avatar" class="chat__header__avatar" />
      <h1 class="chat__header__name">James</h1>
    </header>

    <main class="chat__content">
      <span class="chat__content__time">Yesterday - 4:15pm</span>
      <ChatBox class="chat__content__message" avatar="/assets/images/avatars/michael.jpg" me>Bro, I saw you at the market...<br />I watch your beatiful booty but I think that you need to make more SPORT!! 😁</ChatBox>
      <ChatBox class="chat__content__message" avatar="/assets/images/avatars/Ellipse.png">Bro, just check this out!</ChatBox>
      <span v-if="index > 0" class="chat__content__time">Today - Few seconds ago</span>
      <ChatBox v-if="index > 0" class="chat__content__message" avatar="/assets/images/avatars/michael.jpg" me>Mother fuc***!</ChatBox>
      <ChatBox v-if="index > 1" class="chat__content__message bdl" avatar="/assets/images/avatars/Ellipse.png" border-less>
        <video src="/assets/videos/The%20Ultimate%20Rickroll....mp4" muted autoplay loop></video>
      </ChatBox>
    </main>

    <footer @submit.prevent class="chat__actions">
      <input type="text" class="chat__actions__input" placeholder="Type something..." v-model="message" required />
      <button class="chat__actions__submit" @click="sendMessage"><ion-icon name="send-outline"></ion-icon></button>
    </footer>
  </div>
</template>

<script>
import ChatBox from '../components/ChatBox'
export default {
  name: 'ChatView',
  components: { ChatBox },
  data: () => ({
    index: 0,
    message: ''
  }),
  methods: {
    sendMessage () {
      if (this.message !== 'Mother fucker!') return

      this.message = ''
      this.index = 1
      setTimeout(() => { this.index = 2 }, 2000)
    }
  }
}
</script>

<style lang="scss" scoped>
.chat {
  display: flex;
  height: 100vh;
  flex-direction: column;

  &__header {
    flex: 0 0;
    padding: 1rem;
    display: flex;
    position: relative;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    background-color: #1C1F29;

    &__back {
      top: 1rem;
      left: 1rem;
      font-size: 1.5rem;
      position: absolute;
    }

    &__name {
      font-weight: 600;
      font-size: 1.5rem;
    }
  }

  &__content {
    flex: 1 1;
    display: flex;
    grid-gap: 1rem;
    overflow: auto;
    padding: 1rem 1.5rem;
    flex-direction: column;

    &__time {
      opacity: .3;
      font-size: .75rem;
      align-self: center;
    }

    &__message {
      align-self: flex-end;
      flex-direction: row-reverse;

      &:nth-of-type(2n) {
        flex-direction: row;
        align-self: flex-start;
      }

      &.bdl {
        video {
          width: 100%;
          display: block;
        }
      }
    }
  }

  &__actions {
    flex: 0 0;
    display: flex;
    grid-gap: 2rem;
    padding: 1rem 2rem;
    align-items: center;
    background-color: #1C1F29;

    &__input {
      flex: 1 1;
      width: 100%;
      height: 2rem;
      min-width: auto;
      padding: 0 1rem;
      border-radius: 1rem;
      background-color: #1C1F29;
      box-shadow: -.25rem -.25rem .75rem rgba(255, 255, 255, .15),
                  .25rem .25rem .75rem rgba(0, 0, 0, .35);

      &:focus, &:valid {
        box-shadow: inset -.125rem -.125rem .25rem rgba(255, 255, 255, .15),
                    inset .125rem .125rem .25rem rgba(0, 0, 0, .35);
      }

      &::placeholder {
        opacity: .3;
        color: #f9f9f9;
        font-weight: 400;
      }
    }

    &__submit {
      width: 2rem;
      height: 2rem;
      display: flex;
      flex: 0 0 2rem;
      cursor: pointer;
      border-radius: 100%;
      align-items: center;
      justify-content: center;
      background-color: #DC5050;
    }
  }
}
</style>
