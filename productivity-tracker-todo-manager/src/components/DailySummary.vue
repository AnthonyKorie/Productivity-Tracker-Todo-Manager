<template>
  <v-card elevation="1">
    <v-card-text>
      <p class="dashboard-daily-summary">Daily Summary</p>
      <div class="daily-summary-para">
      Today you had <span class="bold-daily">
        20%
      </span> more meetings than usual, you closed <span class="bold-daily">2 tasks </span> on two projects, but the focus was <span class="bold-daily"> 12% </span>lower then yesterday
      </div>
    </v-card-text>
    <v-divider class="ma-5"></v-divider>

    <v-container fluid class="fill-height">
      <v-row align="center" justify="space-between" class="fill-height">
        <!-- Left Text -->
        <v-col class="text-left daily-summary-para"> Total time worked </v-col>

        <!-- Right Text -->
        <v-col class="text-right daily-summary-para"> Percent of work day </v-col>
      </v-row>
    </v-container>

    <v-container fluid class="fill-height">
      <v-row align="center" justify="space-between" class="fill-height">
        <!-- Left Text -->
        <v-col class="text-left dashboard-daily-summary"> 6 hr 18 min </v-col>

        <!-- Right Text -->
        <v-col class="text-right ">  <span class="dashboard-daily-summary">
          79%
        </span> of 8hr 0min </v-col>
      </v-row>
    </v-container>
    <v-divider class="ma-5"></v-divider>

    <v-row class="ma-2">
      <v-col cols="6">
        <div class="dashboard-daily-summary ml-10 mb-2">Focus</div>
    <div class="donut instalment1">
      <div class="donut-default"></div>
      <div class="donut-line"></div>
      <div class="donut-text">
        <span class="dashboard-daily-summary">62%</span>
      </div>
      <div class="donut-case"></div>
    </div>
      </v-col>
      <v-col cols="6">
        <div class="dashboard-daily-summary ml-10 mb-2">Other</div>
    <div class="donut instalment2">
      <div class="donut-default"></div>
      <div class="donut-line"></div>
      <div class="donut-text">
        <span class="dashboard-daily-summary">12%</span>
      </div>
      <div class="donut-case"></div>
    </div>
      </v-col>

    </v-row>


    <v-divider class="ma-5"></v-divider>

<v-row class="ma-2">
  <v-col cols="6">
    <div class="dashboard-daily-summary ml-10 mb-2">Meetings</div>
<div class="donut instalment1">
  <div class="donut-default"></div>
  <div class="donut-line"></div>
  <div class="donut-text">
    <span class="dashboard-daily-summary">62%</span>
  </div>
  <div class="donut-case"></div>
</div>
  </v-col>
  <v-col cols="6">
    <div class="dashboard-daily-summary ml-10 mb-2">Break</div>
<div class="donut instalment2">
  <div class="donut-default"></div>
  <div class="donut-line"></div>
  <div class="donut-text">
    <span class="dashboard-daily-summary">12%</span>
  </div>
  <div class="donut-case"></div>
</div>
  </v-col>

</v-row>

    <v-divider class="ma-5"></v-divider>
    <v-card-text>
    <p class="daily-summary-para">
      Top Categoris
    </p>
    <v-list subheader two-line>
        <v-list-item v-for="folder in folders" :key="folder.title">
          <v-list-item-content>
            <v-list-item-title class="dashboard-bar-title" v-text="folder.percent"></v-list-item-title>
          </v-list-item-content>
  
          <v-list-item-content >
            <v-list-item-title  class="dashboard-bar-title" v-text="folder.title"></v-list-item-title>
          </v-list-item-content>
  
          <v-list-item-content>
            <v-progress-linear color="primary" :value="folder.value" height="20">
              <strong>{{ Math.ceil(folder.value) }}%</strong>
            </v-progress-linear>
          

          </v-list-item-content>
          
        </v-list-item>
      </v-list>
    </v-card-text>
  </v-card>
</template>
<script>

export default {
  data: () => ({
    reveal: false,
    folders: [
        {
          subtitle: "2hr 58m",
          percent: "47%",
          title: "Desgin",
          value: 47,
        },
        {
          subtitle: "46min",
          percent: "12%",
          value: 12,
  
          title: "Video conference",
        },
        {
          subtitle: "45min",
          percent: "12%",
          value: 12,
  
          title: "Work messaging",
        }
  
        
      ],
  }),
};
</script>
<style>
body {
  font-family: sans-serif;
}

.donut {
  position: relative;
    width: 200px;
    height: 200px;
}

.donut-default {
  width: 100%;
  height: 100%;
  border-radius: 50%;
}

.donut-white {
  width: 80%;
  height: 80%;
  border-radius: 50%;
  background: #fff;
  top: 50%;
  position: absolute;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
}

.donut-line {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
}

.donut-text {
  top: 25px;
  left: 25px;
  width: 150px;
  height: 150px;
  background: #fff;
  position: absolute;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 3;
}

.donut-text span {
  color: #48b2c1;
}

/* ============ instalment 1 ==========*/

.instalment1 .donut-case {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: #48b2c1;
  position: absolute;
  top: 0;
  left: 0;
  background-clip: border-box;
  overflow: hidden;
}

.instalment1 .donut-case::before {
  content: "";
  clip: rect(0 200px 100px 0);
  -webkit-transform: rotate(90deg);
  transform: rotate(180deg);
  background: #cbcb41;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.instalment1 .donut-case::after {
  content: "";
  clip: rect(0 100px 200px 0);
  -webkit-transform: rotate(327.6deg);
  transform: rotate(360deg);
  background: #cbcb41;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.instalment1 .donut-line::before {
  content: "";
  width: 1px;
  height: 100%;
  position: absolute;
  top: -25px;
  left: 50%;
  background: #fff;
  z-index: 2;
}

.instalment1 .donut-line::after {
  content: "";
  width: 100%;
  height: 1px;
  position: absolute;
  top: 50%;
  left: 25px;
  background: #fff;
  border-bottom: 1px solid #fff;
  z-index: 2;
}

/* ============ instalment 2 ==========*/

.instalment2 .donut-case {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: #48b2c1;
  position: absolute;
  top: 0;
  left: 0;
  background-clip: border-box;
  overflow: hidden;
}




.instalment2 .donut-line::before {
  content: "";
  width: 1px;
  height: 100%;
  position: absolute;
  top: 0;
  left: 50%;
  background: #fff;
  z-index: 2;
}

.instalment2 .donut-line::after {
  content: "";
  width: 100%;
  height: 1px;
  position: absolute;
  top: 50%;
  left: 25px;
  background: #fff;
  border-bottom: 1px solid #fff;
  z-index: 2;
}


</style>
