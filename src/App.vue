<template>
  <div id="container-principal" class="container-fluid position-relative h-100">
    <div style="z-index: 9999; width: 100%; right: 0px;" class="position-fixed bg-white">
      <nav id="menu" class="row align-items-center p-2 mx-0 mx-sm-2 mx-md-3 mx-lg-5">
        <div id="logo" class="col-5 col-sm-3 col-md-2">
          <img src="./assets/logo.svg" alt="logo-easybank">
        </div>
        <div class="col-sm-5 col-md-8 d-none d-sm-none d-md-block">
            <div class="container-fluid d-flex justify-content-center text-info">
              <a href="" class="navbar-brand">Home</a>
              <a href="" class="navbar-brand">About</a>
              <a href="" class="navbar-brand">Contact</a>
              <a href="" class="navbar-brand">Blog</a>
              <a href="" class="navbar-brand">Careers</a>
            </div>
        </div>
        <div class="col-7 col-sm-7 col-md-2">
          <img @click="isModalOpen" v-if="!modalOpen" data-bs-toggle="modal" data-bs-target="#exampleModal" class="float-end d-block d-sm-block d-md-none me-4" src="./assets/icon-hamburger.svg" alt="mobile-menu-icon">
          <img @click="isModalOpen" data-bs-dismiss="modal" data-bs-target="#exampleModal" v-else src="./assets/icon-close.svg" class="float-end d-block d-sm-block d-md-none me-4" alt="">
          <button class="d-none d-sm-none d-md-block btn btn-light bg-gradient float-end rounded-pill text-white">
                Request Invite
          </button>
        </div>
        <!-- Menu Mobile -->
        <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
          <div class="modal-dialog">
            <div class="modal-content">
              <ul class="list-group d-flex align-items-center p-3">
                <li class="list-group-item border-0">Home</li>
                <li class="list-group-item border-0">About</li>
                <li class="list-group-item border-0">Contact</li>
                <li class="list-group-item border-0">Blog</li>
                <li class="list-group-item border-0">Careers</li>
              </ul>
            </div>
          </div>
        </div>
    </nav>
    </div>
   <Body/> 
  </div>
</template>

<script>
import { ref } from '@vue/reactivity'
import Body from './layouts/Body.vue'


export default {
  name: 'App',
  components: { Body },
  setup() {
    const modalOpen = ref(false)
    return {
      isModalOpen: () => modalOpen.value = !modalOpen.value,
      modalOpen
    }
  }
}
</script>

<style lang="scss">
#menu{
  height: 85px;
}
  $navbar-brand-font-size: 0.9rem;
  $gradient: linear-gradient(to left, #2bb7da, #00ccd5, #00dcb2, #3ae875);
  $btn-padding-x: 10px;
  $font-family-sans-serif: 'Public Sans', sans-serif;
  $primary:       hsl(233, 26%, 24%);
  $secondary:     hsl(136, 65%, 51%);
  $info:          hsl(233, 8%, 62%);
  $success:       hsl(192, 70%, 51%);
  $light:         hsl(220, 16%, 96%);
  $danger:        #F9F9F9;
  // $modal-backdrop-bg:  linear-gradient(to-left, black, white);
  $container-max-widths: (
  sm: 540px,
  md: 720px,
  lg: 960px,
  xl: 1140px,
  xxl: 1440px
);

.modal{
  top: 90px !important;
}
.container-fluid{
  height: 45px;
}
.container-fluid .navbar-brand:hover{
  border-bottom: 3px solid $secondary;
}
  @import '../node_modules/bootstrap/scss/bootstrap.scss';
</style>
