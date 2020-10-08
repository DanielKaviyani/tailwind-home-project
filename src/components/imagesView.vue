<template>
    <div class="md:relative">
        <div class="sticky top-0 pt-6">
            <div class="grid grid-cols-1 border-2 rounded-lg border-gray-200">
                <img :src="selectedItem.img" :alt="selectedItem.title" />
            </div>
            <div class="grid grid-cols-3 gap-4 mt-6">
                <img
                    v-for="(item, index) in images"
                    :key="index"
                    :src="item.img"
                    :alt="item.title"
                    class="border-2 rounded-lg border-gray-200 focus:border-gray-400 cursor-pointer"
                    :class="{'border-gray-900': item.id === selectedItem.id }"
                    :tabindex="index+1"
                    @click="selectedItem = item"
                    @focus="selectedItem = item"
                />
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ImagesView',
    data: () => ({
        images: [
            { id: 1, img: '/img/kemper-front.jpg', title: 'kemper-front' },
            { id: 2, img: '/img/kemper-angle.jpg', title: 'kemper-angle' },
            { id: 3, img: '/img/kemper-rear.jpg', title: 'kemper-rear' },
        ],
        selectedItem: null
    }),
    created() {
        this.selectedItem = this.images[0]
    },
}
</script>
