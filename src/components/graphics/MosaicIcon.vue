<template>
	<svg xmlns="http://www.w3.org/2000/svg" version="1.0" width="20.000000pt" height="20.000000pt" viewBox="0 0 500.000000 500.000000" preserveAspectRatio="xMidYMid meet" fill="#f2a230">

	</svg>
</template>

<script>
import GraphicComponent from './GraphicComponent.vue';

export default {
	extends: GraphicComponent,

	props: {
		width: {
			type: Number,
			default: 261.333
		},

		height: {
			type: Number,
			default: 131.313
		},

		mosaic: {
			type: Object,
			default: () => ({
				mosaicId: '',
				aliasName: ''
			})
		},

		mosaicId: {
			type: String
		},

		aliasName: {
			type: String
		},

		hideCaption: {
			type: Boolean,
			default: false
		}
	},

	computed: {
		title() {
			return this.getTranslation('mosaic') + ': ' + ((this.aliasName || this.mosaic.aliasName) || (this.mosaicId || this.mosaic.mosaicId));
		},

		iconColor() {
			return this.getIconColorFromHex(this.mosaicId || this.mosaic.mosaicId);
		},

		truncatedMosaicId() {
			return this.truncString(this.mosaicId || this.mosaic.mosaicId);
		},

		truncatedMosaicName() {
			const aliasName = this.aliasName || this.mosaic.aliasName;
			const mosaicId = this.mosaicId || this.mosaic.mosaicId;

			if (aliasName)
				return this.truncString(aliasName, 5);
			return this.truncString(mosaicId);
		},

		viewBox() {
			return this.hideCaption
				? '115 0 16 105'
				: '0 0 261.333 131.313';
			// 0 0 116 105
		}
	}
};
</script>

<style lang="scss" scoped>
.connector {
    cursor: pointer;
}

.connector-body {
    font-size: 18px;
    font-weight: bold;
}

.mosaic-text {
    font-size: 18px;
    font-weight: bold;
    fill: var(--secondary);
}
</style>


