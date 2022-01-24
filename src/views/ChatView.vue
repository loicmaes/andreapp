<template>
  <div class="chat">
    <header class="chat__header">
      <router-link to="/" class="chat__header__back"><ion-icon name="return-down-back-outline"></ion-icon></router-link>
      <img src="/assets/images/avatars/Ellipse.png" alt="James Avatar" class="chat__header__avatar" />
      <h1 class="chat__header__name">James</h1>
    </header>

    <main class="chat__content">

    </main>

    <footer @submit.prevent class="chat__actions">
      <input type="text" class="chat__actions__input" placeholder="Type something..." required />
      <button class="chat__actions__submit"><ion-icon name="send-outline"></ion-icon></button>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'ChatView'
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
