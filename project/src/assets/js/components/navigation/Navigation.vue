<template>
    <nav
        :class="expanded ? 'nav-expanded' : ''"
    >
        <div class="logo">Utility tools</div>
        <div class="nav-container">
            <router-link to="/" @click="closeExpand">Home</router-link>
            <router-link to="/percentage-calculator" @click="closeExpand">Percentage calculator</router-link>
            <router-link to="/temperature-converter" @click="closeExpand">Temperature converter</router-link>
            <router-link to="/weight-converter" @click="closeExpand">Weight converter</router-link>
            <router-link to="/speed-converter" @click="closeExpand">Speed converter</router-link>
            <div class="made-with">Slasher © {{ currentYear }}</div>
        </div>
        <div 
            class="menu-icon d-inline-flex d-lg-none"
            @click="toggleExpand">
            <input class="menu-icon__cheeckbox" type="checkbox" />
            <div>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>
</template>

<script>

export default {
    name: 'VueNavigation',
    data() {
        return {
            expanded: false,
            currentYear: null,
        };
    },
    mounted() {
        this.getCurrentYear();
    },
    methods: {
        toggleExpand() {
            this.expanded = this.expanded === false;
            this.scrollToTop();
        },
        closeExpand() {
            this.expanded = false;
            this.scrollToTop();
        },
        scrollToTop() {
            window.scrollTo(0,0);
        },
        getCurrentYear() {
            return this.currentYear = new Date().getFullYear();
        }
    },
};
</script>