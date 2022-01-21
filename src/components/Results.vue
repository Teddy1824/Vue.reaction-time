<template>
        <p>Reaction time - {{ score }}</p>
        <p class="speed">{{ speed }}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            speed: null
        }
    },

    mounted() {
        if(this.score < 250) {
            this.speed = "Very fast"
        }

        else if (this.score < 400) {
            this.speed = "Relatively fast"
        }

        else {
            this.speed = "Not so fast, try again."
        }
    }
}
</script>

<style>
    .speed {
        font-size: 1.4em;
        color: #0faf87;
        font-weight: bold;
    }

    button {
        background: #0faf82;
        color: white;
        border: none;
        padding: 8px 16px;
        border-radius: 4px;
        letter-spacing: 1px;
        cursor: pointer;
        margin: 10px;
    }

    button[disabled] {
        opacity: 0.2;
        cursor: not-allowed;
    }
</style>