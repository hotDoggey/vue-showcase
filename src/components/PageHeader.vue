<template>
    <div class="top_ribon">
        <!-- prettier-ignore -->
        <font-awesome-icon icon="fa-solid fa-car-burst" size="2xl" />

        <!-- <img @click="print" alt="Logo" class="logo" src="@\assets\logo.png" /> -->
        <h1 class="title">{{ title }}</h1>

        <nav>
            <router-link to="/">Home</router-link> |
            <router-link :to="{ name: 'about' }">About</router-link> |
            <router-link :to="{ name: 'jobs' }">Jobs</router-link>
        </nav>
    </div>
</template>

<script>
export default {
    props: [`title`],
};
</script>

<style scoped>
.top_ribon {
    display: flex;
    padding: 0pt 10pt 0pt 30pt;
    background: var(--primary-color);
    color: whitesmoke;
}
.top_ribon > * {
    /* border: 15px solid orange;  <<< uncomment this to see effect of *star* */
    /* border: 15px solid orange; */
    margin: 15px;
}
img.logo {
    height: 35px;
    width: 35px;
    border-radius: 20%;
}
.title {
    height: 40%;
    margin-top: auto;
    margin-bottom: auto;
}
nav {
    padding-top: auto;
}
nav a {
    font-weight: bold;
    color: whitesmoke;
}
nav a.router-link-exact-active {
    color: whitesmoke;
}
</style>
