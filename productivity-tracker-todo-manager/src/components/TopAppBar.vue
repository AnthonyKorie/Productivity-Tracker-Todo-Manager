<template>
  <v-card elevation="1">
    <v-container fluid class="fill-height">
      <v-row align="center" justify="space-between" class="fill-height">
        <!-- Left Text -->
        <v-col class="text-left">
          <p class="top-bar-date ml-2 mt-8">
            {{ getCurrentDateInfo() }}
          </p>
        </v-col>

        <!-- Right Text -->
        <v-col class="text-right">
          <v-btn-toggle v-model="toggle_exclusive" mandatory>
            <v-btn
              :class="toggle_exclusive != 0 ? 'black--text' : 'white--text'"
              :color="toggle_exclusive != 0 ? 'white' : 'black'"
            >
              day
            </v-btn>
            <v-btn
              :class="toggle_exclusive != 1 ? 'black--text' : 'white--text'"
              :color="toggle_exclusive != 1 ? 'white' : 'black'"
            >
              week
            </v-btn>
            <v-btn
              :class="toggle_exclusive != 2 ? 'black--text' : 'white--text'"
              :color="toggle_exclusive != 2 ? 'white' : 'black'"
            >
              month
            </v-btn>
          </v-btn-toggle>

          <span class="ml-10">
            <v-btn large color="white" class="black--text"> Today </v-btn>
          </span>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      toggle_exclusive: 0,
    };
  },
  methods: {
    getCurrentDateInfo() {
      const currentDate = new Date();

      const dayOfWeek = currentDate.toLocaleDateString("en-US", {
        weekday: "long",
      });
      const month = currentDate.toLocaleDateString("en-US", { month: "long" });
      const dayOfMonth = currentDate.getDate();
      const year = currentDate.getFullYear();

      return dayOfWeek + ", " + month + ", " + dayOfMonth + ", " + year;
    },
  },
};
</script>
