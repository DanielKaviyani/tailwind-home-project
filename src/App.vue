<template>
    <div id="app">
        <div class="relative">
            <div class="container px-3 md:px-auto md:mx-auto pb-12">
                <app-header />
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 md:mt-12">
                    <images-view />
                    <app-details :form="form" />
                </div>
            </div>
            <app-footer :form="form" />
        </div>
    </div>
</template>

<script>
export default {
    name: "App",
    data: () => ({
        form: {
            price: 2717,
            factor: 'none',
            amp: 'none',
            foot: 'none',
        },
    }),
    components: {
        appHeader: () => import('@/components/appHeader'),
        appFooter: () => import('@/components/appFooter'),
        imagesView: () => import('@/components/imagesView'),
        appDetails: () => import('@/components/details')
    },
};
</script>

<style scoped>
body {
    font-family: Inter, 'Courier New', Courier, monospace;
}
</style>