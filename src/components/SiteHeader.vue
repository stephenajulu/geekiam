<template>
    <header >
        <nav class="container mx-auto flex flex-wrap justify-between items-center py-8">
            <div>
                <g-link to="/" class="text-green-800 text-base no-underline hover:text-green-600 hover:no-underline">
                    <g-image src="~/assets/images/logo.svg" :alt="$static.metadata.siteName" class="h-10"/>
                </g-link>
            </div>
             <div class="block lg:hidden">
                    <button @click="toggle" class="flex items-center px-3 py-2 border rounded border-gray-500 hover:text-gray-600 hover:border-gray-600">
                        <svg class="current-color h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" fill="gray" /></svg>
                    </button>
                </div>
                <ul class="uppercase tracking-wide font-bold w-full flex-grow lg:flex lg:flex-initial lg:w-auto
                items-center mt-8 lg:mt-0 " :class="expand ? 'block' : 'hidden'" >
                    <li class="mr-8 mb-6 lg:mb-0 text-green-800"><g-link to="/blog" class="text-copy-primary hover:text-gray-600">Blog</g-link></li>
                    <li class="mr-8 mb-6 lg:mb-0 text-green-800"><g-link to="/tutorial" class="text-copy-primary hover:text-gray-600">Tutorials</g-link></li>
                    <li class="mr-8 mb-6 lg:mb-0 text-green-800"><g-link to="/about" class="text-copy-primary hover:text-gray-600">About</g-link></li>
                </ul>
        </nav>
    </header>
</template>

<script>

    export default {
        name: "SiteHeader",
        data() {
            return {
                expand: false
            }
        },
        methods: {
            toggle() {
                this.expand = !this.expand
            }
        }
    }
</script>

<style scoped>

</style>

<static-query>
    query {
    metadata {
    siteName
    siteUrl
    }
    }
</static-query>

