<template>
    <div class="temperature-converter-page">
        <h1>Temperature converter</h1>
        <p class="mb-4">Convert temperature.</p>
        <CelsiusToFahrenheit/>
        <CelsiusToKelvin/>
        <FahrenheitToCelsius/>
        <FahrenheitToKelvin/>
        <KelvinToCelsius/>
        <KelvinToFahrenheit/>
    </div>
</template>

<script setup>
import CelsiusToFahrenheit from '../components/temperature/CelsiusToFahrenheit.vue';
import FahrenheitToCelsius from '../components/temperature/FahrenheitToCelsius.vue';
import CelsiusToKelvin from '../components/temperature/CelsiusToKelvin.vue';
import KelvinToCelsius from '../components/temperature/KelvinToCelsius.vue';
import FahrenheitToKelvin from '../components/temperature/FahrenheitToKelvin.vue'
import KelvinToFahrenheit from "../components/temperature/KelvinToFahrenheit.vue";
</script>