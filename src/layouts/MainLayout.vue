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
            <a class="btn-floating btn-large blue" href="#">
                <i class="large material-icons">add</i>
            </a>
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