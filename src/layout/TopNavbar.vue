<template>
  <nav class="navbar navbar-expand-lg">
    <div class="container-fluid">

      <div class="container">
        <div class="row">
          <div class="col-3">
            <div class="logo-img">
                <img src="img/unjfsc.png" alt="">
            </div>
          </div>
          
          <div class="col-9">
            <br>
            <a>Universidad Nacional Faustino Sanchez Carrion</a>
            <br>
            <a>Unidad de registros y escalafon</a>
          </div>
        </div>
      </div>

    
      <button type="button"
              class="navbar-toggler navbar-toggler-right"
              :class="{toggled: $sidebar.showSidebar}"
              aria-controls="navigation-index"
              aria-expanded="false"
              aria-label="Toggle navigation"
              @click="toggleSidebar">
        <span class="navbar-toggler-bar burger-lines"></span>
        <span class="navbar-toggler-bar burger-lines"></span>
        <span class="navbar-toggler-bar burger-lines"></span>
      </button>
      <div class="collapse navbar-collapse justify-content-end">
        
        
        <ul class="navbar-nav ml-auto">
          <base-dropdown tag="li">
            <template slot="title">
              <i class="nc-icon nc-grid-45"></i>
              
            </template>
            <a class="dropdown-item" href="#">Perfil</a>
            <a class="dropdown-item" href="#">Ayuda</a>
            <a class="dropdown-item" href="#">Cambiar Contraseña</a>
            <a class="dropdown-item" href="#">Cerrar Sesion</a>
          </base-dropdown>
        </ul>

      </div>
    </div>
  </nav>
</template>
<script>
  export default {
    computed: {
      routeName () {
        const {name} = this.$route
        return this.capitalizeFirstLetter(name)
      }
    },
    data () {
      return {
        activeNotifications: false
      }
    },
    methods: {
      capitalizeFirstLetter (string) {
        return string.charAt(0).toUpperCase() + string.slice(1)
      },
      toggleNotificationDropDown () {
        this.activeNotifications = !this.activeNotifications
      },
      closeDropDown () {
        this.activeNotifications = false
      },
      toggleSidebar () {
        this.$sidebar.displaySidebar(!this.$sidebar.showSidebar)
      },
      hideSidebar () {
        this.$sidebar.displaySidebar(false)
      }
    }
  }

</script>
<style>

</style>
