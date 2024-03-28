<template>
    <div class="h-full relative">
        <div class="hidden h-full md:flex md:w-72 md:flex-col md:fixed ms:inset-y-0 z-80">
            <Sidebar/>
            <!-- sidebar -->
        </div>
        <main class="md:pl-72 pb-10">
            <!-- Navbar -->
            <slot/>
        </main>
    </div>
</template>

<script setup lang="ts">
import Sidebar from '../components/ui/Sidebar.vue';


</script>

<style scoped>

</style>