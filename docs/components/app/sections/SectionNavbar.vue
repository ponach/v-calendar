<template>
<section>
  <nav class='navbar is-transparent' role='navigation' aria-label='main navigation'>
    <div class='container'>
      <div class='navbar-brand'>
        <router-link class='navbar-item is-size-4 has-text-primary has-text-weight-semibold' to='/'>
          V-Calendar
        </router-link>
        <span
          class='span navbar-burger'
          :class='{ "is-active": isMenuActive }'
          @click='isMenuActive = !isMenuActive'>
          <span></span>
          <span></span>
          <span></span>
        </span>
      </div>
      <div class='navbar-menu' :class='{ "is-active": isMenuActive }'>
        <div class='navbar-end'>
          <router-link class='navbar-item is-hidden-desktop' to='/' exact><a>Calendar</a></router-link>
          <router-link class='navbar-item is-hidden-desktop' to='/datepicker'><a>Date Picker</a></router-link>
          <router-link class='navbar-item is-hidden-desktop' to='/gallery'><a>Gallery</a></router-link>
          <router-link class='navbar-item is-hidden-desktop' to='/setup'><a>Setup</a></router-link>
          <a class='navbar-item' title='Github' href='https://github.com/nathanreyes/v-calendar' target='_blank'>
            <b-icon icon='github'></b-icon>
          </a>
          <a class='navbar-item' href='https://github.com/nathanreyes/v-calendar/blob/master/CHANGELOG.md' target='_blank'>Changelogs</a>
        </div>
      </div>
    </div>
  </nav>
</section>
</template>

<script>
import Package from '@/../package.json';

export default {
  data() {
    return {
      isMenuActive: false,
      version: Package.version,
    };
  },
  watch: {
    $route() {
      this.isMenuActive = false;
    },
  },
};
</script>

<style lang='sass' scoped>

.menu-enter-active, .menu-leave-active
  transition: all 0.3s
  background-color: transparent

.menu-enter, .menu-leave-to
  transform: translateY(-30px)
  opacity: 0

</style>
