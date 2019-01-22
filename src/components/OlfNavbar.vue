<template>
    <nav class="navbar navbar-expand-md navbar-light fixed-top">
        <div class="container-fluid">
            <div class="navbar-brand d-flex mr-auto">
                <a href="/">
                    <img src="/assets/olf-logo.png" v-if="!$slots['logo']" />
                    <slot name="logo"></slot>
                </a>
            </div>

            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#collapsingNavbarMenu">
                <span class="navbar-toggler-icon"></span>
            </button>

            <div class="collapse navbar-collapse" id="collapsingNavbarMenu">
                <ul class="navbar-nav ml-auto">
                    <li class="nav-item" v-for="item in menu">
                        <a class="nav-link" :href="item.path">{{item.name}}</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    props: {
        menu: Array
    }
}
</script>

<style lang="scss">
.navbar-brand {
    a {
        * {
            width: auto;
            max-height: 35px;
        }
    }
}
</style>
