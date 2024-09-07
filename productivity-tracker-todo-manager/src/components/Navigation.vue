<!-- eslint-disable -->
<template>
  <div>
    <v-navigation-drawer class="deep-white accent-4" permanent fixed app width="300">
      <template v-slot:prepend>
        <v-list-item two-line class="ma-5">
          <v-list-item-avatar tile>
            <v-img src="@/assets/logo.png" max-height="50" contain></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title class="logo">FocusForge.</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </template>

      <v-divider></v-divider>
      <v-list class="ma-2 nav-list">
        <v-list-item-group
          v-model="group"
          active-class="deep-black--text text--accent-4"
        >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
          @click="handleItemClick(item)"
          :class="{ clicked: clickedItem === item }"
        >
          <v-list-item-icon :color="clickedItem === item ? 'primary' : ''">
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content :color="clickedItem === item ? 'primary' : ''">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        </v-list-item-group>
      </v-list>

      <template v-slot:append>
        <v-list class="ma-2 nav-list">
          <v-list-item v-for="item in bottom" :key="item.title" link>
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </template>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { title: "Dashboard", icon: "mdi mdi-view-dashboard", link : "/" },
        { title: "Calendar", icon: "mdi mdi-calendar-account-outline" , link : "/calendar"  },
        { title: "Project & tasks", icon: "mdi mdi-file-tree", link : "/project"  },
        { title: "To-Do", icon: "mdi mdi-timer-cog-outline", link : "/todo"  },
        { title: "History", icon: "mdi mdi-clipboard-text-clock", link : "/"  },
      ],
      bottom: [
        { title: "Logout", icon: "mdi mdi-logout" },
        { title: "Help", icon: "mdi mdi-help-box" },
        { title: "Settings", icon: "mdi mdi-cogs" },
      ],
      clickedItem: null,
      group: null,
    };
  },
  methods: {
    handleItemClick(item) {
      this.clickedItem = item;
      // Add any additional logic you want to perform on item click
    },
  },
};
</script>
<style scoped>
.clicked {
  background: grey;
}


</style>
