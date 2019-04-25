<template>
	<div id="index">
		<!--<mt-button size="large" @click="go">测试跳转</mt-button>-->
		<!--<div v-for="item in nameList">
			<span>{{item.name}}</span>
			<span>{{item.obj}}</span>
		</div>-->
	</div>
</template>
<style scoped>
	#index {
		display: flex;
		justify-content: center;
		margin-top: 100px;
	}
</style>
<script>
	export default {
		data() {
			return {
				nameList: []
			}
		},
		created() {
			   this.$http.get('/api/test.json').then((response) => {

				console.log(response.data)
				//响应正确回调
				this.nameList = response.body; //把数据存放到data中
			})
		},

		/*methods: {
			go() {
				this.$router.push('/fa');
			},

		}*/

	}
</script>