<template>
	<svg
		version="1.1"
		xmlns="http://www.w3.org/2000/svg"
		xmlns:xlink="http://www.w3.org/1999/xlink"
		:x="_x"
		:y="_y"
		width="38.5px"
		height="38.167px"
		viewBox="0 0 38.5 38.167"
		xml:space="preserve"
		class="circle-icon"
	>
		<defs>
			<linearGradient id="native-mosaic-circle-gradient" x1="0%" y1="0%" x2="100%" y2="100%">
				<stop offset="0%" stop-color="RGB(242, 114, 255)" />
				<stop offset="100%" stop-color="RGB(233, 42, 255)" />
			</linearGradient>
		</defs>
		<foreignObject x="446" y="318" width="100" height="100">
			<MosaicListPopover
				:target="id"
				:mosaics="mosaics"
			/>
		</foreignObject>
		<circle
			id="native-mosaic-circle"
			fill-rule="evenodd"
			clip-rule="evenodd"
			fill="#EC2227"
			cx="19.115"
			cy="19.094"
			r="17.26"
		/>
		<g>
		</g>
		<circle
			:id="id"
			fill-rule="evenodd"
			clip-rule="evenodd"
			fill="transparent"
			cx="19.115"
			cy="19.094"
			r="17.26"
		/>
	</svg>
</template>

<script>
import GraphicComponent from './GraphicComponent.vue';
import MosaicListPopover from './MosaicListPopover.vue';

export default {
	extends: GraphicComponent,

	components: {
		MosaicListPopover
	},

	props: {
		mosaics: {
			type: Array,
			default: () => []
		}
	},

	data() {
		return {
			id: this.getId('native-mosaic-circle')
		};
	}
};
</script>

<style lang="scss" scoped>
.connector-shadow {
    fill: #ebebeb;
}
</style>
