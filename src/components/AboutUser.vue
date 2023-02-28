<template>
  <div class="about-user">
    <p class="for-user"><span>You are changing the password for user:</span></p>
    <p class="user-id">User ID: <span class="id-value">{{userId}}</span></p>
    <p class="email">Email: <span class="email-value">{{email}}</span></p>
  </div>
</template>

<script>
export default {
  name: 'AboutUser',
  props: {
    userId: {
      type: String,
      required: true
    },
    email: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped lang="scss">

.about-user {
  font-size: calc(12px + 4 * (100vw / 1280));
  @media(max-width:767px){
    font-size: calc(12px + (4 + 4 * 0.7) * ((100vw - 320px) / 1280));
    padding: 1.2rem 0;
  }
  text-align: center;
  .for-user{
    margin-bottom: 1.2rem;
  }
  .user-id {
    margin-bottom: 0.4rem;
  }
  .id-value {
    font-weight: bold;
  }
  .email {
    margin-bottom: 0.5rem;
  }
  .email-value {
    font-weight: bold;
  }
}

</style>
