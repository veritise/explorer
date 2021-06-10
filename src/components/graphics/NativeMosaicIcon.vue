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
		}
	},

	computed: {
		title() {
			return this.getTranslation('mosaic') + ': ' + this.nativeMosaicAliasName;
		},

		mosaicId() {
			return this.nativeMosaicId;
		},

		aliasName() {
			return this.nativeMosaicAliasName;
		}
	},

	methods: {
		click() {
			this.$emit('click', this.mosaicId);
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
</style>
