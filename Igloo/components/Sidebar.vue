
<template>
	<div id="app">
			<div class=" fixed flex top-0 h-screen z-20 text-white " :class="[right ? 'right-0 flex-row' : 'left-0 flex-row-reverse']">
				<button
					@click.prevent="toggle()"
					class="w-10 h-32 p-1 my-auto rounded text-white bg-opacity-75 bg-purple-500 text-center focus:outline-none hover:bg-blue-200 transition-color duration-300">
					<span :class="[right ? '-rotate-90' : 'rotate-90']" class="block transform origin-center font-bold">
						Leita
					</span>
				</button>
				<div ref="content" class="transition-all duration-700 bg-slate-400 overflow-hidden  items-center justify-center" :class="[open ? 'max-w-lg' : 'max-w-0']">
                    <div class="ml-4 mt-44">
					    <div class="w-48 font-bold text-xl flex font-serif text-purple-500">Leita</div>
                        <div class=" mt-2">
                            <p> location</p>
                            <input placeholder="Staðsetning" class="mr-3 rounded-md text-black">
                            
                            <button class=" bg-purple-500 rounded-md p-1 mr-2">Staðfesta</button>
                        </div>
                        <div class="flex flex-col mt-7 border-b border-purple-500 mr-3">
                            <Label for="dist" class="">Distance</Label>
                            <select name="dist" id="dis" class="mr-6 h-7 bg-white rounded-md text-gray-400 mb-4 ">
                                <option value="">Akstur</option>
                                <option value="">Undir 50.000 KM</option>
                                <option value="">Yfir 50.000 KM </option>
                                <option value="">Undir 100.000 KM </option>
                                <option value="">Yfir 100.000 KM</option>
                            </select>
                        </div>
                        <div>
                            <p class="mt-5 mb-2 font-bold text-lg">Nánari Leit</p>
                            <input type="checkbox" id="4x4" name="extra" value="4x4" checked />
                            <label for="coding">4x4</label>
                        </div>
                        <div>
                            <input type="checkbox" id="BT" name="extra" value="Bluetooth" />
                            <label for="music">Bluetooth</label>
                        </div>
                        <div>
                            <input type="checkbox" id="sjalf" name="extra" value="Sjálfskiptur" />
                            <label for="music">Sjálfskiptur</label>
                        </div>
                        <div>
                            <input type="checkbox" id="bein" name="extra" value="Beinskiptur" />
                            <label for="music">Beinskiptur</label>
                        </div>
                        <button class="bg-purple-500 mt-5 rounded-md ml-3 p-2">Staðfesta</button>
                    </div>
				</div>
			</div>
			<transition name="fade">
				<div v-if="dimmer && open" @click="toggle()" class="flex-1 bg-gray-400 bg-opacity-75 active:outline-none z-10"/>
			</transition>
	</div>
</template>

<script>
export default {
	data() {
		return {
			open: false,
			dimmer: true,
			right: false
		};
	},
	methods: {
		toggle() {
			this.open = !this.open;
		}
	}
};
</script>

<style>
html {
	background: #efefef;
}

.fade-enter-active,
.fade-leave-active {
	transition: opacity 1s ease-out;
}

.fade-enter,
.fade-leave-to {
	opacity: 0;
}
</style>