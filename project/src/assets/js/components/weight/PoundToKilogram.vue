<template>
    <div class="percent-calc card-v1">
        <div class="calc-04">
            <div class="title">Pound to kilogram</div>
            <div class="calc">
                <span class="copy">What is</span>
                <input
                    v-model="number01"
                    type="number"
                    class="number-01"
                    @input="convertWeight()"
                >
                <span class="copy">lbs in kg?</span>

                <span class="result">
                    {{ animatedResult }} kg
                </span>
            </div>
        </div>
    </div>
</template>

<script>
import gsap from "gsap";

export default {
    name: 'PoundToKilogram',
    data() {
        return {
            number01: null,
            constant: 0.45359237,
            result: 0,
            tweenedNumber: 0,
        };
    },
    computed: {
        animatedResult: function() {
            return this.tweenedNumber.toFixed(4);
        }
    },
    watch: {
        result: function(newValue) {
            gsap.to(this.$data, { duration: 0.5, tweenedNumber: newValue });
        }
    },
    methods: {
        convertWeight() {
            this.result = this.number01 * this.constant;
        },
    },
};
</script>