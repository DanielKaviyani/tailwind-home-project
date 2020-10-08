<template>
    <div class="sticky bottom-0 bg-gray-50">
        <div class="bg-gray-200 height-1"></div>
        <div class="container mx-auto">
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 p-3">
                <div class="hidden sm:block lg:hidden">
                    <div class="flex text-sm text-gray-900 mb-3">
                        <img :src="img1" alt="" width="20px" height="auto" class="mr-3" />
                        Free Shipping
                    </div>
                    <div class="flex text-sm text-gray-900">
                        <img :src="img2" alt="" width="20px" height="auto" class="mr-3" />
                        2 Year Warranty
                    </div>
                </div>
                <div class="hidden lg:block">
                    <div class="flex text-sm text-gray-900">
                        <img :src="img1" alt="" width="20px" height="auto" class="mr-3" />
                        Free Shipping
                    </div>
                    <div class="text-sm text-gray-500">
                        Get 2-day free shipping anywhere in North America.
                    </div>
                </div>
                <div class="hidden lg:block">
                    <div class="flex text-sm text-gray-900">
                        <img :src="img2" alt="" width="20px" height="auto" class="mr-3" />
                        2 Year Warranty
                    </div>
                    <div class="text-sm text-gray-500">
                        If anything goes wrong in the first two years, we'll replace it for free.
                    </div>
                </div>
                <div class="flex justify-end">
                    <div class="flex items-center">
                        <div class="mr-6">
                            <div class="text-xl font-bold text-gray-900 text-right">
                                ${{ Intl.NumberFormat().format(form.price) }}
                            </div>
                            <div class="hidden sm:block text-sm text-gray-500">
                                Need financing?
                                <a href="#" class="border-b-2">
                                    Learn more
                                </a>
                            </div>
                        </div>
                        <button class="bg-gray-900 text-white p-3 rounded-lg focus:outline-none">
                            Buy now
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'AppFooter',
    props: {
        form: {
            type: Object,
            default: () => {}
        },
    },
    data: () => ({
        img1: require('@/assets/icons/globe-icon.svg'),
        img2: require('@/assets/icons/shield-check-icon.svg')
    }),
}
</script>

<style scoped>
.height-1 {
    height: 1px;
}
</style>
