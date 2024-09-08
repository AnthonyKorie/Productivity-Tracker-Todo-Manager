<template>
  <div>
    <v-list subheader two-line>
      <v-list-item v-for="folder in folders" :key="folder.title">
        <v-list-item-content class="dashboard-bar-title">
          <v-list-item-title v-text="folder.percent"></v-list-item-title>
        </v-list-item-content>

        <v-list-item-content class="dashboard-bar-title">
          <v-list-item-title v-text="folder.title"></v-list-item-title>
        </v-list-item-content>

        <v-list-item-content>
          <v-progress-linear :value="folder.value" height="20">
            <strong>{{ Math.ceil(folder.value) }}%</strong>
          </v-progress-linear>
          <v-list-item-title v-text="folder.subtitle"></v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </div>
</template>

<script>
export default {
  data: () => ({
    folders: [
      {
        subtitle: "3hr 26 min",
        percent: "49%",
        title: "FinWall App",
        value: 49,
      },
      {
        subtitle: "1hr 47 min",
        percent: "32%",
        value: 32,

        title: "FinWall Web",
      },
      {
        subtitle: "46 min",
        percent: "14",
        value: 14,

        title: "Terminal App",
      },

      {
        subtitle: "19 min",
        value: 5,

        percent: "5%",

        title: "Li.Fi App",
      },
    ],
  }),
};
</script>
