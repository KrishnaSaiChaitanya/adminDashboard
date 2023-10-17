<template>
  <div v-if="isSidebarOpen" class="sidebar" :data-expanded="isSidebarOpen">
    <div class="sidebar-header">Logo</div>
    <div class="sidebar-menu">
      <div v-for="(section, index) in sidebarData" :key="index">
        <p class="sidebar-section">{{ section.section }}</p>
        <ul>
          <li v-for="(menu, menuIndex) in section.menus" :key="menuIndex"
            :style="{ backgroundColor: menu.active && menu.id == menuIndex ? '#445' : 'no color' }">
            <div style="display: flex; justify-content: space-between;">
              <p style="marginBottom: 0.1rem">{{ menu.name }}</p>
              <!-- Conditionally render the icon if submenus exist -->
              <svg v-if="menu.submenus && menu.submenus.length > 0" @click="toggleDropdown(menu.id)" :style="{
                width: '16px',
                marginLeft: '32px',
                marginBottom: '0.1rem',
                transform: menu.active ? 'rotate(180deg)' : 'rotate(0deg)'
              }" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                <path :stroke="menu.active ? 'white' : 'currentColor'" stroke-linecap="round" stroke-linejoin="round"
                  stroke-width="2" d="m1 1 4 4 4-4" />
              </svg>
            </div>
            <!-- Conditionally render submenus if they exist -->
            <ul v-if="menu.submenus && menu.submenus.length > 0" v-show="menu.active">
              <li v-for="(submenu, submenuIndex) in menu.submenus" :key="submenuIndex">
                {{ submenu.name }}
              </li>
            </ul>
          </li>
        </ul>
      </div>
    </div>
  </div>
  <div class="menuBtn" @click="toggleSidebar" :data-expanded="isSidebarOpen">
    <svg v-if="!isSidebarOpen" aria-hidden="true" style="z-index: 11; width: 21px; color: black"
      xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
      <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
        d="M1 1h15M1 7h15M1 13h15" />
    </svg>
    <svg v-if="isSidebarOpen" style="z-index: 11; width: 18px; color: white" aria-hidden="true"
      xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 14">
      <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
        d="m1 1 6 6m0 0 6 6M7 7l6-6M7 7l-6 6" />
    </svg>
  </div>
</template>


<script>
export default {
  data() {
    return {
      isSidebarOpen: window.innerWidth > 768,
      sidebarData: [
        {
          section: "Section 1",
          menus: [
            {
              id: 'dropdown1',
              name: "Menu 1",
              active: false,
              submenus: [
                { name: "Submenu 1" },
                { name: "Submenu 2" },
              ],
            },
            {
              id: 'dropdown2',
              name: "Menu 2",
              active: false,
              submenus: [
                { name: "Submenu 3" },
                { name: "Submenu 4" },
              ],
            },
          ],
        },
        {
          section: "Section 2",
          menus: [
            {
              id: 'dropdown3',
              name: "Menu 1",
              active: false,
              submenus: [
                { name: "Submenu 1" },
                { name: "Submenu 2" },
              ],
            },
          ],
        },
        {
          section: "Section 3",
          menus: [
            {
              id: 'dropdown4',
              name: "Normal menu",
              active: false,
            },
          ],
        },
      ],
    };
  },
  created() {
    window.addEventListener("resize", this.handleResize);
  },
  destroyed() {
    window.removeEventListener("resize", this.handleResize);
  },
  methods: {
    toggleDropdown(id) {
      for (let section of this.sidebarData) {
        for (let menu of section.menus) {
          menu.active = menu.id === id && !menu.active;
        }
      }
    },
    toggleSidebar() {
      this.isSidebarOpen = !this.isSidebarOpen;
    },
    handleResize() {
      this.isSidebarOpen = window.innerWidth > 768;
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
  overflow-y: scroll;
  top: 0;
  left: 0;
  z-index: 10;
  transition: 0.3s;
}

.sidebar-header {
  padding: 20px;
  font-size: 20px;
  font-weight: 700;
  text-align: center;
}

.sidebar-section {
  font-size: 18px;
  padding-left: 10px;
  font-weight: 500;

}

.sidebar-menu ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.sidebar-menu {
  padding: 5px;
}

.sidebar-menu ul li {
  cursor: pointer;
  box-shadow: rgba(0, 0, 0, 0.05) 0px 0px 0px 1px;
  border-radius: 10px;
  padding: 10px;
  margin: 4px;
  border: 1px solid #555;
  position: relative;
  user-select: none;
  transition: 0.2s;
}

.sidebar-menu ul li:hover {
  background-color: rgb(113, 112, 112);
}

.sidebar-menu ul li ul {
  margin-top: 10px;
  /* background-color: #555; */
  position: relative;
  top: -3px;
}

.sidebar-menu ul li ul li {
  padding: 6px 12px;
  border-bottom: 1px solid #555;
}

.sidebar-menu ul li ul li:hover {
  /* padding: 10px 20px; */
  /* border-bottom: 1px solid #555; */
  background-color: #444;
}

.menu-button {
  display: flex;
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

  .sidebar[data-expanded="false"] {
    display: none;
  }

  .sidebar[data-expanded="true"] {
    width: 80%;
  }

  .sidebar.open {
    width: 20%;
  }

  .sidebar-slide-enter-active,
  .sidebar-slide-leave-active {
    transition: transform 0.3s;
  }

  .sidebar-slide-enter,
  .sidebar-slide-leave-to {
    transform: translateX(-250px);
  }

  .menuBtn[data-expanded="true"] {
    background-color: white;
    border-radius: 50%;
    width: 30px;
    height: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .crossBtn {
    width: 10px;
    height: 12px;
  }

  .menuBtn {
    position: absolute;
    top: 3%;
    left: 5%;
  }
}
</style>












