<template>
    <!-- prettier-ignore   -->
    <PageHeader title="CarCheck" :router="$router"/>
    <button @click="redirect">Redirect</button>
    <button @click="back">Go Back</button>
    <button @click="forward">Go Forward</button>

    <router-view />
    <!-- router-view is where the content of each component page is displayed, as nav is separate it will always be shown at the top of all pages -->
    <PageFooter
        id="page-footer"
        footer_content="Lorem ipsum dolor sit amet consectetur adipisicing elit. Iure cumcum animi suscipit. Quae aut reprehenderit dicta
            repellendssimus corporis quas sit amet optio fugiat numquam omnis iure."
    ></PageFooter>
</template>

<script>
export default {
    name: "App",
    components: {},
    data() {
        return {
            showBar: false,
            buffer: 50,
        };
    },
    mounted() {
        window.addEventListener("scroll", this.handleScroll);
    },
    beforeDestroy() {
        window.removeEventListener("scroll", this.handleScroll);
    },
    methods: {
        handleScroll() {
            const distanceFromTop = window.pageYOffset + window.innerHeight;
            const documentHeight = document.body.scrollHeight;

            if (distanceFromTop >= documentHeight - this.buffer) {
                this.showBar = true;
            } else {
                this.showBar = false;
            }
        },
        redirect() {
            this.$router.push({ name: "home" });
        },
        back() {
            this.$router.go(-1);
        },
        forward() {
            this.$router.go(1);
        },
    },
};
</script>

<style>
:root {
    --primary-color: #2c3e50;
}
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: var(--primary-color);
}

button {
    margin: 0 10px;
    padding: 10px;
    border: none;
    border-radius: 4px;
}

#app {
    min-height: 100vh;
}

#page-footer {
    position: sticky;
    top: 100%;
    height: 5vh;
    background-color: #333;
    color: #fff;
}
#page-footer.show {
    bottom: 0; /* move the bar up to show it */
}
</style>
