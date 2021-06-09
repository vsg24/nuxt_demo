<template>
	<div class="mapouter">
		<iframe width="100%" class="gmap_canvas"
				src="https://maps.google.com/maps?q=2880%20Broadway,%20New%20York&t=&z=13&ie=UTF8&iwloc=&output=embed"
				frameborder="0" scrolling="no" marginheight="0" marginwidth="0"></iframe>
	</div>
</template>

<style>
.mapouter {
	position: relative;
	text-align: right;
	height: 100%;
	width: 100%;
}

.gmap_canvas {
	overflow: hidden;
	background: none !important;
	height: 335px;
	width: 100%;
}
</style>
