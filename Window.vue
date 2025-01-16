<script setup>

	const emit = defineEmits(['extFunc']);
	
	const props = defineProps({
		caption: {
			type: String,
			default: 'Заголовок окна',
			},
		});

	const handleClick = () => {
			// emit('click', isActive.value)
			emit('extFunc', { timestamp: Date.now() })
			};



</script>

<template>
	<div class="iq-window-background">

		<div class="iq-window">
			<div class="iq-window-title">
				<div class="iq-window-title-caption">{{caption}}</div>
				<div class="iq-window-close"> [ ] </div>
			</div>
			<div class="iq-window-body">
				<slot>
					
				</slot>
			</div>
		</div>
	</div>
		

	<!-- <div>1</div>
	<div class="test">AAAAA</div>
	<div>1</div>
	<button @click="handleClick">[!!!]</button> -->
	
	
</template>

<style lang="scss" scoped>

.test{
	&:hover{background-color: aqua;}
	}
@mixin max(){
	top: 0;
	bottom: 0;
	left: 0;
	right: 0;
	}

.iq-window-background{
	@include max();
	position: fixed;
	background: rgba(0, 0, 0, 0.5);
	display: flex;
	z-index: 1000;
	align-items: center;
	justify-content: center;
	}
.iq-window{
	border: 2px solid gray;
	box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
	max-width: 90vw;
	max-height: 90vh;
	min-width: 300px;

	position: fixed;
	background-color: white;
	color:black;
	z-index: 1001;
	overflow-y: auto;
	}

</style>