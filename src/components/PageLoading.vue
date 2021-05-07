<template>
<section class="page-loading" :style="styleObject">
	<!-- 动图 -->
	<img class="loading" src="../assets/page-animation.gif" alt="翻页加载动画">
</section>
</template>

<script>
export default {
	name: 'pageLoading',
	props: {
		option: Object
	},
	data() {
		return {
			styleObject: {
				'top': '40px',
				'bottom': '60px'
			}
		}
	},
	created() {
		// 重新设置位置
		if (this.option && this.option.top) {
			this.styleObject.top = this.option.top;
		}
		if (this.option && this.option.bottom) {
			this.styleObject.bottom = this.option.bottom;
		}
	}
}
</script>

<style lang="scss">
.page-loading {
    position: fixed;
    // top: 40px;
    left: 0;
    right: 0;
    // bottom: 60px;
    z-index: 99999;
    background-color: #fff;

    img.loading {
        position: absolute;
        left: 50%;
		top: 50%;
		// 往上（x轴）,左（y轴）移动自身长宽的 50%，以使其居于中心位置。
		// transform: translate(-50%,-100%);
		transform: translate(-50%,-50%);
        width: 20%;
    }
}
</style>
