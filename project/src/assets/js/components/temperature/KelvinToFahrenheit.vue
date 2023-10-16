<template>
    <div class="percent-calc card-v1">
        <div class="calc-04">
            <div class="title">Kelvin to Fahrenheit</div>
            <div class="calc">
                <span class="copy">What is</span>
                <input
                    v-model="number01"
                    type="number"
                    class="number-01"
                    @input="convertTemperature"
                >
                <span class="copy">K in Fahrenheit?</span>

                <span class="result">
                    {{ animatedResult }} °F
                </span>
            </div>
        </div>
    </div>
</template>

<script>
import gsap from "gsap";

export default {
    name: 'KelvinToFahrenheit',
    data() {
        return {
            number01: null,
            constant: 273.15,
            result: 0,
            tweenedNumber: 0,
        };
    },
    computed: {
        animatedResult: function() {
            return this.tweenedNumber.toFixed(1);
        }
    },
    watch: {
        result: function(newValue) {
            gsap.to(this.$data, { duration: 0.5, tweenedNumber: newValue });
        }
    },
    methods: {
        convertTemperature() {
            this.result = (this.number01 - this.constant) * 9/5 + 32;
        },
    },
};
</script>