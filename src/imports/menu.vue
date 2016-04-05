<script>
  import VcModal from './modal.vue'

  export default {
    components:{ VcModal },

    methods:{
      openModal () {
       	this.$broadcast('open-modal')
       },
      closeModal () {
        this.$broadcast('close-modal')
      },
      toggleHeight () {
			this.$broadcast('open-modal')
      },
    },

  }
</script>
<template>
	<div>
		<div id="menu-icon-wrapper" class="menu-icon-wrapper" style="visibility: visible;">
			<svg width="1000px" height="1000px">
					<path id="pathA" d="M 300 400 L 700 400 C 900 400 900 750 600 850 A 400 400 0 0 1 200 200 L 800 800" style="stroke-dashoffset: 5803.15; stroke-dasharray: 2901.57, 2981.57, 240;"></path>
					<path id="pathB" d="M 300 500 L 700 500" style="stroke-dashoffset: 800; stroke-dasharray: 400, 480, 240;"></path>
					<path id="pathC" d="M 700 600 L 300 600 C 100 600 100 200 400 150 A 400 380 0 1 1 200 800 L 800 200" style="stroke-dashoffset: 6993.11; stroke-dasharray: 3496.56, 3576.56, 240;"></path>
			</svg>
			<button id="menu-icon-trigger" 
				@click="toggleHeight()" 
				class="menu-icon-trigger">
			</button>
		</div>
	</div>

	 <vc-modal titulo="Titulo do modal"></vc-modal>

</template>
<style>
	/* Menu icon styles */
.menu-icon-wrapper {
	position: fixed;
	display: inline-block;
    width: 34px;
    height: 34px;
	margin: 2em;
	right: 0;
	pointer-events: none;
	transition: 0.1s;
	z-index: 99999;
}


.menu-icon-wrapper svg {
	position: absolute;
	top: -33px;
	left: -33px;
	-webkit-transform: scale(0.1);
	-ms-transform: scale(0.1);
	transform: scale(0.1);
	-webkit-transform-origin: 0 0;
	-ms-transform-origin: 0 0;
	transform-origin: 0 0;
}

.menu-icon-wrapper svg path {
	stroke: #fff;
	stroke-width: 60px;
	stroke-linecap: round;
    stroke-linejoin: round;
	fill: transparent;
}

.menu-icon-wrapper .menu-icon-trigger {
	position: relative;
	width: 100%;
	height: 100%;
	cursor: pointer;
	pointer-events: auto;
	background: none;
	border: none;
	margin: 0;
	padding: 0;
}

.menu-icon-wrapper .menu-icon-trigger:hover,
.menu-icon-wrapper .menu-icon-trigger:focus {
	outline: none;
}

</style>
