<template>
    <div>
        <div class="text-gray-500">
            Starting at
        </div>
        <div class="text-gray-900 mb-6 text-4xl font-bold">
            $1,799
        </div>
        <p class="text-gray-900 mb-3">
            The KEMPER PROFILER™ is the leading-edge digital guitar amplifier and all-in-one effects processor.
        </p>
        <p class="text-gray-500 mb-3">
            Hailed as a game-changer by guitarists the world over, the PROFILER™ is the first digital guitar amp to really nail the full and dynamic sound of a guitar or bass amp.
        </p>
        <p class="text-gray-500 mb-6">
            This is made possible by a radical, patented technology and concept which we call "PROFILING".
        </p>
        <!-- Form Factor -->
        <div class="text-gray-900 mb-2 font-bold">
            Form Factor
        </div>
        <div class="grid grid-cols-1 gap-4 sm:grid-cols-2 mb-6">
            <div
                class="p-3 border-2 border-gray-300 rounded-lg cursor-pointer focus:border-gray-400"
                tabindex="4"
                :class="{'border-gray-900': form.factor === 'none'}"
                @click="form.factor = 'none'"
                @focus="form.factor = 'none'"
            >
                <div class="text-gray-900 mb-3">Profiler Head</div>
                <div class="text-gray-500">
                    Compact amplifier head, perfect for a speaker cabinet or desk.
                </div>
            </div>
            <div
                class="p-3 border-2 border-gray-300 rounded-lg cursor-pointer focus:border-gray-400"
                tabindex="5"
                :class="{'border-gray-900': form.factor === 'profiler'}"
                @click="form.factor = 'profiler'"
                @focus="form.factor = 'profiler'"
            >
                <div class="text-gray-900 mb-3">Profiler Rack</div>
                <div class="text-gray-500">
                    3U rackmount version of the classic profiling amplifier.
                </div>
            </div>
        </div>
        <!-- Form Factor -->
        <!-- Power Amp -->
        <div class="text-gray-900 mb-2 font-bold">
            Power Amp
        </div>
        <div class="grid grid-cols-1 gap-4 mb-6">
            <div
                class="p-3 border-2 rounded-lg cursor-pointer" 
                :class="{'border-gray-900': form.amp === 'none'}"
                tabindex="6"
                @click="amp_handler('none')"
                @focus="amp_handler('none')"
            >
                <div class="text-gray-900 mb-3">None</div>
                <div class="text-gray-500">
                    Use in the studio or with your own power amp.
                </div>
            </div>
            <div
                class="flex items-center p-3 border-2 rounded-lg cursor-pointer"
                :class="{'border-gray-900': form.amp === 'powered'}"
                tabindex="7"
                @click="amp_handler('powered')"
                @focus="amp_handler('powered')"
            >
                <div class="flex-1">
                    <div class="text-gray-900 mb-3">Powered</div>
                    <div class="text-gray-500">
                        Built-in 600W solid state power amp.
                    </div>
                </div>
                <div class="text-gray-900">+ $449</div>
            </div>
        </div>
        <!-- Power Amp -->
        <!-- Foot Controller -->
        <div class="text-gray-900 mb-2 font-bold">
            Foot Controller
        </div>
        <div class="grid grid-cols-1 gap-4 mb-6">
            <div
                class="p-3 border-2 rounded-lg cursor-pointer"
                tabindex="8"
                :class="{'border-gray-900': form.foot === 'none'}"
                @click="foot_handler('none')"
                @focus="foot_handler('none')"
            >
                <div class="text-gray-900 mb-3">None</div>
            </div>
            <div
                class="flex items-center p-3 border-2 rounded-lg cursor-pointer"
                tabindex="9"
                :class="{'border-gray-900': form.foot === 'profiler'}"
                @click="foot_handler('profiler')"
                @focus="foot_handler('profiler')"
            >
                <div class="flex-1">
                    <div class="text-gray-900 mb-3">
                        Profiler Remote Foot Controller
                    </div>
                </div>
                <div class="text-gray-900">+ $449</div>
            </div>
        </div>
        <!-- Foot Controller -->
        <!-- Specifications -->
        <div class="divide-y divide-gray-300">
            <div class="text-gray-900 mb-2 font-bold">
                Specifications
            </div>
            <div
                v-for="(item, index) in details"
                :key="index"
                class="flex justify-between py-3"
            >
                <span class="text-sm">{{ item.title }}</span>
                <span class="text-sm">{{ item.value }}</span>
            </div>
            <div></div>
        </div>
        <!-- Specifications -->
    </div>
</template>

<script>
export default {
    name: 'Details',
    props: {
        form: {
            type: Object,
            default: () => {}
        },
    },
    data: () => ({
        details: [
            { title: 'Amp Models', value: '200' },
            { title: 'Effects Loop', value: 'Yes' },
            { title: 'Inputs', value: '2 x 1/4”' },
            { title: 'Outputs', value: '1 x 1/4”, 2 x XLR, 2 x 1/4”' },
            { title: 'MIDI I/O', value: 'In/Out/Thru' },
            { title: 'Width', value: '14.88”' },
            { title: 'Depth', value: '6.81”' },
            { title: 'Weight', value: '11.73 lbs' }
        ],
    }),
    methods: {
        amp_handler(val) {
            if (val === 'none' && this.form.amp != 'none') {
                this.form.price -= 449
            } else if ((val === 'powered' && this.form.amp != 'powered')) {
                this.form.price += 449
            }
            this.form.amp = val
        },
        foot_handler(val) {
            if (val === 'none' && this.form.foot != 'none') {
                this.form.price -= 449
            } else if ((val === 'profiler' && this.form.foot != 'profiler')) {
                this.form.price += 449
            }
            this.form.foot = val
        },
    },
}
</script>
