<template>
    <div style="width: 100%; display: flex;">
        <div class="sidebar-layout">
            <Sidebar />
        </div>
        <div class="main-dashboard">
            <HelloWorld />
        </div>
    </div>
</template>

<script setup>
import HelloWorld from './HelloWorld.vue';
import Sidebar from './Sidebar.vue';

</script>

<style>
.sidebar-layout {
    width: 20%;
}

.main-dashboard {
    width: 80%;
}

@media (min-width: 1024px) {
    .sidebar-layout {
        width: 20%;
    }

    .main-dashboard {
        width: 80%;
    }
}

/* Media query for mobile and tablet views */
@media (max-width: 700px) {
    .sidebar-layout {
        width: 0;
    }

    .main-dashboard {
        width: 100%;
    }
}
</style>