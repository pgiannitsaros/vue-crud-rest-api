<template>
    <div id="app">

<!--        <ul class="nav-bar">-->
<!--            <li>-->
<!--                <router-link to="/page-1">Page 1</router-link>-->
<!--            </li>-->
<!--            <li>-->
<!--                <router-link to="/page-2">Page 2</router-link>-->
<!--            </li>-->
<!--            <li>-->
<!--                <router-link to="/page-3">Page 3</router-link>-->
<!--            </li>-->
<!--        </ul>-->


        <div><b-navbar toggleable="lg" type="dark" variant="info">
            <b-navbar-brand href="#">NavBar</b-navbar-brand>

            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

            <b-collapse id="nav-collapse" is-nav>
                <b-navbar-nav>
                    <b-nav-item to="/page-1">Tasks</b-nav-item>
                    <b-nav-item to="/page-2">Page 2</b-nav-item>
                    <b-nav-item to="/page-3">Page 3</b-nav-item>
                </b-navbar-nav>

                <!-- Right aligned nav items -->
                <b-navbar-nav class="ml-auto">
                    <b-nav-form>
                        <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
                        <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
                    </b-nav-form>

                    <b-nav-item-dropdown text="Lang" right>
                        <b-dropdown-item href="#">EN</b-dropdown-item>
                        <b-dropdown-item href="#">ES</b-dropdown-item>
                        <b-dropdown-item href="#">RU</b-dropdown-item>
                        <b-dropdown-item href="#">FA</b-dropdown-item>
                    </b-nav-item-dropdown>

                    <b-nav-item-dropdown right>
                        <!-- Using 'button-content' slot -->
                        <template v-slot:button-content>
                            <em>User</em>
                        </template>
                        <b-dropdown-item href="#">Profile</b-dropdown-item>
                        <b-dropdown-item href="#">Sign Out</b-dropdown-item>
                    </b-nav-item-dropdown>
                </b-navbar-nav>
            </b-collapse>
        </b-navbar>
        </div>
        <router-view class="view" :stored2="compStored"></router-view>
    </div>
</template>

<script>

    export default {
        name: 'app',
        components: {},
        data: () => ({stored: '123'}),
        methods: {
            updateStore: function (val) {
                this.stored = val;
            },
        },
        computed: {
            compStored: () => {
                return 'comp val';
            }
        }
    }
</script>

<style scoped>
    .nav-bar {
        list-style-type: none;
        overflow: hidden;
    }

    .nav-bar li {
        float: left;
        margin-left: 10px;
        text-decoration: none;
    }
</style>

