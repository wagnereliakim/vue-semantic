<template>
    <div :class="loadingClasses">{{ text }}</div>
</template>

<script>
    export default {
        props: {
            active: {
                default: true,
            },
            text: {
                default: 'Loading...',
            },
            size: {},
            inline: {},
            inverted: {},
            centered: {},
        },

        computed: {
            loadingClasses() {
                const classes = {
                    ui: true,
                    loader: true,
                    text: this.text ? true : false,
                    active: this.active ? true : false,
                    inline: typeof this.inline !== 'undefined' ? true : false,
                    inverted: typeof this.inverted !== 'undefined' ? true : false,
                    centered: typeof this.centered !== 'undefined' ? true : false,
                }

                if (this.size) {
                    classes[this.size] = true
                }

                return classes
            },
        },
    }
</script>
