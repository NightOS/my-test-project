<template>
	<div>
		<div class="warper">
			<img :src="seller.avatar">
			<div>
				<div>
					<h3>
						<img src="">
						{{seller.name}}
					</h3>
				</div>
				<p>{{seller.description}}/{{seller.deliveryTime}}分钟送达</p>
				<p v-if="seller.supports">{{seller.supports[0].description}}</p>
				<button @click="showCover">5个></button>
			</div>
			<div>
				{{seller.bulletin}}
			</div>			
		</div>
		<div v-show="coverShow" class="cover">
			<h4>{{seller.name}}</h4>
			<p>优惠信息</p>
			<ul class="supports">
				<li v-for="supports in seller.supports">
					{{supports.description}}
				</li>
			</ul>
			<p>商家公告</p>
			<p>{{seller.bulletin}}</p>
			<button @click="hideCover">coverHide</button>
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
				coverShow:false
			}
		},
		methods:{
			showCover(){
				this.coverShow = true;
			},
			hideCover(){
				this.coverShow = false;
			}
		}

	}
</script>
<style type="text/css">
</style>