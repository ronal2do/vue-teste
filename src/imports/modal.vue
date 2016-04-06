<script>
	export default {
		
		props: ['titulo'],
		
		events:{
			'open-modal'(){
				 this.isVisible = !this.isVisible
			},

		},

		data () {
			return {
				isVisible: false
			}
		},

		methods:{
			open() {
				this.isVisible = true
			},
			close() {
				this.isVisible = false
			},
			
		},
	}
</script>
<template>
	<div id="modal">
		<div class="vc-overlay" 
			:class="{ 'vc-modal-show': isVisible, 
			'vc-modal-hide': !isVisible }"></div>
		<div class="vc-modal" 
			:class="{ 'vc-modal-show': isVisible, 
					  'vc-modal-hide': !isVisible }">
			<div class="vc-modal-header">
				<h4>{{ titulo }}</h4>
				
			</div>
			<div class="vc-modal-body">
				<slot></slot>
			</div>
		</div>
	</div>
</template>
<style scoped>
	.vc-modal-cloase{
		width: 20px;
		height: 20px;
		cursor: pointer;
		position: absolute;
		top: 10px;
		right: 6px;
	}
	.vc-modal-show{
		opacity: 1;
		transition: opacity 400ms easy;
		z-index: 10000;
	}
	.vc-modal-hide{
		opacity: 0;
		transition: opacity 400ms easy; z-index: 1s;
		z-index: -10000;
	}
	.vc-overlay{
		background-color: rgba(0,0,0,0.1);
		position: fixed;
		top: 0;
		right: 0;
		bottom: 0;
		left: 0;
	}
	.vc-modal{
		width: 300px;
		height: 400px;
		background-color: #f4f4f4;
		border-bottom: #aaa 1px solid;
		position: fixed;
		top: 50%;
		left: 50%;
		margin-top: -200px;
		margin-left: -150px;
		border-radius: 6px;
		box-shadow: 0 0 10px 10px rgba(0, 0, 0, 0.2);
	}
	.vc-modal-header h4{
		margin:0;
		padding: 0 10px;
	}
	.vc-modal-header{
		border-bottom: #aaa 1px solid;
		margin:10px 0;
		position: relative;
	}
	.vc-modal-body{
		padding:15px;
	}
</style>