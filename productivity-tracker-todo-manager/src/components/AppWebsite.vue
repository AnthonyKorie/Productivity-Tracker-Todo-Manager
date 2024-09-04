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
        subtitle: "2hr 58 min",
        percent: "47%",
        title: "Figma",
        value: 47,
      },
      {
        subtitle: "46 min",
        percent: "12%",
        value: 12,

        title: "Adobe",
      },
      {
        subtitle: "45 min",
        percent: "12%",
        value: 12,

        title: "Zoom.us",
      },

      {
        subtitle: "26 min",
        value: 7,

        percent: "7%",

        title: "Slack",
      },

      {
        subtitle: "23 min",
        value: 6,

        percent: "6%",

        title: "Pinterest",
      },

      {
        subtitle: "11 min",
        value: 3,

        percent: "3%",

        title: "Facebook",
      },

      {
        subtitle: "11 min",
        value: 3,

        percent: "3%",

        title: "Instagram",
      },

      {
        subtitle: "30 min",
        value: 6,

        percent: "6%",

        title: "Twitch",
      },
      {
        subtitle: "2 hr",
        value: 20,

        percent: "20%",

        title: "Youtube",
      },
      {
        subtitle: "19 min",
        value: 5,

        percent: "5%",

        title: "Other",
      },
    ],
  }),
};
</script>
