<template>
    <div class="percent-calc card-v1 calc-01">
        <div class="calc-01">
            <div class="title">Kilogram to Pound</div>
            <div class="calc">
                <span class="copy">What is</span>
                <input
                    v-model="number01"
                    type="number"
                    class="number-01"
                    @input="convertWeight()"
                >
                <span class="copy">kg in pounds?</span>

                <span class="result">
                    {{ animatedResult }} lbs
                </span>
            </div>
        </div>
        <div v-if="settings.toggled" class="settings">
            Adjust decimal point:<br>

            <div class="d-flex align-items-center py-1">
                <span
                    class="material-symbols-outlined cursor-pointer selection-none"
                    @click="settings[0].decimalPoint = settings[0].decimalPoint - 1"
                    v-html="'remove'"
                />
                <span class="selection-none mx-1">{{ settings[0].decimalPoint }}</span>
                <span
                    class="material-symbols-outlined cursor-pointer selection-none"
                    @click="settings[0].decimalPoint = settings[0].decimalPoint + 1"
                    v-html="'add'"
                />
            </div>
            0.<span
                v-for="point in settings[0].decimalPoint" 
                :key="point.id"
            >
                <span>{{ point }}</span>
            </span>
        </div>
        <span
            class="material-symbols-outlined cursor-pointer icon"
            @click="settings.toggled = !settings.toggled"
            v-html="settings.toggled ? 'close':'tune'"
        />
    </div>
</template>

<script>
import gsap from "gsap";

export default {
    name: 'KilogramToPound',
    data() {
        return {
            number01: null,
            constant: 0.45359237,
            result: 0,
            tweenedNumber: 0,
            settings: [{
                toggled: false,
                decimalPoint: 4,
            }],
        };
    },
    computed: {
        animatedResult: function() {
            return this.tweenedNumber.toFixed(this.settings[0].decimalPoint);
        }
    },
    watch: {
        result: function(newValue) {
            gsap.to(this.$data, { duration: 0.5, tweenedNumber: newValue });
        }
    },
    methods: {
        convertWeight() {
            this.result = this.number01 / this.constant;
        },
    },
};
</script>