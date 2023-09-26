<template>
    <br>
    <br>
    <ul>
        <div v-for="part in introParts">
            <p>{{ part }}</p>
            <br>
        </div>
    </ul><link rel="stylesheet" href="style.css">
    <div class="image_container">
        <img
        width="250"
        heigh="250"
        :src="imagePath"
        alt="My Image">
    </div>
</template>

<script>
export default { 
    data() {
        return {
        imagePath: '/src/assets/photographs/profile.png',
        introParts: []
        }
    },
    created() {
        this.introParts = this.introParts.concat(`Hello, and welcome! I've created this page to showcase my work and my interests.`,
                    `I see myself as a connector - I love connecting people and ideas.`, 
                    `What can I make or help make? How can I help other people? I'm always searching for answers to these questions - they are two of my greatest motivators. I take pride in contributing to projects that enable us to lead healthy and rewarding lives.`)
    }
}
</script>

<style>

.image_container {
    display: flex;
    justify-content: center;
    margin: 1em 1em;
}

</style>