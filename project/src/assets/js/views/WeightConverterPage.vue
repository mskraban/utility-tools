<template>
    <div class="weight-converter-page">
        <h1>Weight converter</h1>
        <p class="mb-4">Convert weight.</p>
        <KilogramToPound/>
        <PoundToKilogram/>
        <gram-to-ounce/>
        <ounce-to-gram/>
    </div>
</template>

<script setup>
import KilogramToPound from "../components/weight/KilogramToPound.vue";
import PoundToKilogram from "../components/weight/PoundToKilogram.vue";
import GramToOunce from "../components/weight/GramToOunce.vue";
import OunceToGram from "../components/weight/OunceToGram.vue";
</script>