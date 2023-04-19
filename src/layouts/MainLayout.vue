<template>
    <div class="app-main-layout">

      <NavbarNavigation/>
      <SidebarNavigation />

    
        <main class="app-content">
            <div class="app-page">
                <router-view/>
            </div>
        </main>
    
        <div class="fixed-action-btn">
            <router-link class="btn-floating btn-large blue" to="/record">
                <i class="large material-icons">add</i>
            </router-link>
        </div>
    </div>
</template>

<script>
import NavbarNavigation from '@/components/app/NavbarNavigation.vue';
import SidebarNavigation from '@/components/app/SidebarNavigation.vue';

export default{
  components: {
    NavbarNavigation,SidebarNavigation
  }
}

</script>