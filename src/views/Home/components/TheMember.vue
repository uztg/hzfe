<template>
  <section class="home-section member">
    <header>
      <div class="rect-skew_brown">
        <h2>Member</h2>
      </div>
    </header>
    <section class="main">
      <template v-for="member in members" v-if="members">
        <MemberCard :member="member"></MemberCard>
      </template>
    </section>
    <footer>
      <img src="static/img/Seedling.svg" alt="Seedling" aria-hidden="true">
    </footer>
  </section>
</template>

<script>
import MemberCard from './MemberCard.vue'
import memebers from '../../../members.json'

export default {
  name: 'TheMember',
  components: {
    MemberCard
  },
  data () {
    return {
      members: memebers
    }
  }
}
</script>

<style scoped lang="scss">
  @import '~style';

  .member {
    height: 100vh;
    background-color: $yellow;
    @include flex-cross-center(flex, column);
    justify-content: space-between;
  }
  .main {
    width: 100%;
    @include flex-center;
    flex-wrap: wrap;
    align-content: center;
    padding: 0 5vw;

    &::after {
      content: '';
      flex: 1;
    }
  }
  @include max-screen($media-ip6p) {
    .main::after {
      display: none;
    }
  }
</style>
