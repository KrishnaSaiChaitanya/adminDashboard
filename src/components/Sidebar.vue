<template>
    <div class="sidebar">
        <div class="sidebar-header">
            Sidebar Header
        </div>
        <button class="menu-button" @click="toggleSidebar">Menu</button>
        <transition name="sidebar-slide">
            <div class="sidebar-menu" v-if="isSidebarOpen">
                <ul>
                    <li @click="toggleDropdown('dropdown1')">
                        Menu 1
                        <ul v-show="activeDropdown === 'dropdown1'">
                            <li>Submenu 1</li>
                            <li>Submenu 2</li>
                        </ul>
                    </li>
                    <li @click="toggleDropdown('dropdown2')">
                        Menu 2
                        <ul v-show="activeDropdown === 'dropdown2'">
                            <li>Submenu 3</li>
                            <li>Submenu 4</li>
                        </ul>
                    </li>
                </ul>
            </div>
        </transition>
    </div>
</template>

<script>
export default {
    data() {
        return {
            activeDropdown: '',
            isSidebarOpen: true, // Set to true to keep the sidebar open initially
        };
    },
    methods: {
        toggleDropdown(dropdown) {
            if (this.activeDropdown === dropdown) {
                this.activeDropdown = '';
            } else {
                this.activeDropdown = dropdown;
            }
        },
        toggleSidebar() {
            this.isSidebarOpen = !this.isSidebarOpen;
        },
    },
};
</script>

<style scoped>
.sidebar {
    width: 20%;
    background-color: #333;
    color: #fff;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    transition: 0.3s;
}

.sidebar-header {
    padding: 20px;
    text-align: center;
}

.sidebar-menu ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

.sidebar-menu ul li {
    cursor: pointer;
    padding: 10px;
    border-bottom: 1px solid #555;
    position: relative;
    user-select: none;
    transition: 0.2s;
}

.sidebar-menu ul li:hover {
    background-color: #555;
}

.sidebar-menu ul li ul {
    margin-top: 10px;
    background-color: #444;
    position: relative;
    top: -3px;
}

.sidebar-menu ul li ul li {
    padding: 10px 20px;
    border-bottom: 1px solid #555;
}

.menu-button {
    display: none;
    /* Initially hidden on large screens */
    background-color: #555;
    color: #fff;
    border: none;
    padding: 10px;
    cursor: pointer;
    width: 100%;
    text-align: left;
}

@media (max-width: 768px) {
    .menu-button {
        display: block;
        /* Show the menu button on small screens */
    }

    .sidebar {
        width: 0;
    }

    .sidebar.open {
        width: 250px;
    }

    .sidebar-slide-enter-active,
    .sidebar-slide-leave-active {
        transition: transform 0.3s;
    }

    .sidebar-slide-enter,
    .sidebar-slide-leave-to {
        transform: translateX(-250px);
    }
}
</style>
