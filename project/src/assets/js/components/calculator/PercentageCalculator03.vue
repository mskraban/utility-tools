<template>
    <div class="percent-calc card-v1 calc-02">
        <div class="calc-01">
            <div class="title">Get percent difference between 2 numbers</div>
            <div class="calc">
                <input
                    v-model="number01"
                    type="number"
                    class="number-01"
                    @input="calculatePercentage"
                >
                <span class="copy">is what percent of</span>
                <input
                    v-model="number02"
                    type="number"
                    class="number-02"
                    @input="calculatePercentage"
                >
                <span class="result">
                    Result: {{ animatedResult }}%
                </span>
            </div>
        </div>
    </div>
</template>

<script>
import gsap from "gsap";

export default {
    name: 'PercentageCalculator02',
    data() {
        return {
            number01: null,
            number02: null,
            result: 0,
            tweenedNumber: 0,
        };
    },
    computed: {
        animatedResult: function() {
            return Math.round(this.tweenedNumber * 100) / 100;
        }
    },
    watch: {
        result: function (newValue) {
            gsap.to(this.$data, {duration: 0.5, tweenedNumber: newValue});
        },
    },
    methods: {
        calculatePercentage() {
            this.result = ((this.number01 - this.number02) / this.number01) * (-100);
        },
    },
};
</script>