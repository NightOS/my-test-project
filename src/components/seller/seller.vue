<template>
	<div>
		<div class="ratingsTop">
			<div>
				<p>{{seller.name}}</p>
				<p><span>({{seller.ratingCount}})</span><span>月售{{seller.sellCount}}单</span></p>	
			</div>
			<div class="collection">
				<div @click="clickHeart" :class="['heart',{'heartColor':heartstate}]"></div>
				<p>{{favoriteText}}</p>
			</div>
		</div>
		<div>
			<div>
				<p></p>
				<p></p>
			</div>
			<div>
				<p></p>
				<p></p>
			</div>
			<div>
				<p></p>
				<p></p>
			</div>
		</div>
	</div>
</template>
<script type="text/javascript">
	export default {
		props:{
			seller:{
				type:Object
			}
		},
		data(){
			return {
				heartstate:false
			}
		},
		methods:{
			clickHeart(){
				this.heartstate = !this.heartstate;

			}
		},
		computed:{
			favoriteText(){
				return this.heartstate ? "收藏" : "未收藏";
			}
		}
	}
</script>
<style type="text/css">
	.heart{
		width: 30px;
		height:30px;
		border:1px solid #333; 
	}
	.heartColor{
		background-color: red;
	}
	.ratingsTop div{
		display: inline-block;
	}
</style>