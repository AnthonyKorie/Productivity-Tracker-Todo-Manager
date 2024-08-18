<template>
  <v-app>
    <v-main  style="background-color: black;">
      <Navigation />
      <!-- TimeLine -->
      <v-row ma-2 >
         
        <v-col cols="12">
          <TopAppBar />
        </v-col>
        <v-col cols="8" class="mt-1">
          <v-card elevation="1">
            <v-card-title class="dashboard-title"> Timeline </v-card-title>
            <v-card-text>
              <TimeLine />
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="4" class="mt-1">
          <DailySummary />
        </v-col>

        <v-col cols="4" class="mt-1">
          <v-card elevation="1">
            <v-card-title class="dashboard-title"> Project & Tasks </v-card-title>
            <v-card-text>
          <ProjectTasks />
          </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="4" class="mt-1">
          <v-card elevation="1">
            <v-card-title class="dashboard-title"> Apps & Websites </v-card-title>
            <v-card-text>
          <AppWebsite />
          </v-card-text>
          </v-card>
        </v-col>
        
      </v-row>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
  created(){
    this.$vuetify.theme.isDark = true
  }
};
</script>
