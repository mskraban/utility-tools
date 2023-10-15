<template>
    <div class="weight-converter-page">
        <h1>Speed converter</h1>
        <p class="mb-4">Convert speed.</p>
        <kilometer-to-mile/>
        <mile-to-kilometer/>
    </div>
</template>

<script setup>
import KilometerToMile from "../components/speed/KilometerToMile.vue";
import MileToKilometer from "../components/speed/MileToKilometer.vue";
</script>