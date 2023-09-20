<template>
    <div class="home">
        <h1>Home</h1>
        <p>Utility tools homepage</p>
        <section class="apps">
          <router-link
              to="/percentage-calculator"
              class="app-card card-v1"
          >
            <div class="app-img">
              <span class="material-symbols-outlined">percent</span>
            </div>
            <div class="app-title">
              Percent calculator
            </div>
          </router-link>
          <router-link
              to="/temperature-converter"
              class="app-card card-v1"
          >
            <div class="app-img">
              <span class="material-symbols-outlined">device_thermostat</span>
            </div>
            <div class="app-title">
              Temperature converter
            </div>
          </router-link>
          <router-link
              to="/weight-converter"
              class="app-card card-v1"
          >
            <div class="app-img">
              <span class="material-symbols-outlined">weight</span>
            </div>
            <div class="app-title">
              Weight converter
            </div>
          </router-link>
        </section>
    </div>
</template>