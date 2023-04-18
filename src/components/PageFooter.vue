<template>
    <div class="page_footer">
        <span class="footer_content">{{ footer_content }}</span>
    </div>
</template>

<script>
export default {
    props: [`footer_content`],
};
</script>

<style scoped>
.page_footer {
    display: flex;
    padding: 0pt 10pt 0pt 30pt;
    background: var(--primary-color);
    color: whitesmoke;
}
.page_footer > * {
    /* border: 15px solid orange;  <<< uncomment this to see effect of *star* */
    /* border: 15px solid orange; */
    margin: 15px;
}

.footer_content {
    height: 40%;
    margin-top: auto;
    margin-bottom: auto;
}
</style>
