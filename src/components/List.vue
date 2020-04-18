<template>
    <div>
        <div>
            VR Games list
        </div>
        <ul class="container">
            <li v-for="site of sites" v-bind:key="site.url" class="site">
                <a v-bind:href="site.url" class="site-title">
                    {{ site.name }} <br /><br />
                    <img v-bind:src="site.img" class="site-img" />
                </a>
            </li>
        </ul>
    </div>
</template>

<script>

    import sites from '../sites.json'

    export default {
        name: 'List',
        data: () => ({
            sites
        }),
    }
</script>

<style scoped>
    .container {
        background-color: lightgray;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        list-style: none;
        margin-top: 20px;
        padding: 0;
        width: 100%;
    }

    .site {
        background: #FAFAFA;
        border: 2px solid #CCC;
        border-radius: 5px;
        margin: 2px 5px 10px 5px;
        padding-top: 10px;
        position: relative;
        width: 30%;
        transition: all .2s;
    }

    .site:hover {
        background: rgb(214, 205, 194);
        border: 2px solid rgb(57, 112, 105);
    }

    @media (min-width: 350px) {
        .site {
            width: 90%;
        }
    }

    @media (min-width: 700px) {
        .site {
            width: 45%;
        }
    }

    @media (min-width: 1100px) {
        .site {
            width: 30%;
        }
    }

    .site-img {
        width: 100%;
        max-height: 300px;
    }

    .site-title {
        font-size: 25px;
        text-decoration: none;
        font-weight: bold;
        color: rgb(5, 110, 129);
    }

</style>
