/*--------------------------------------------------------------------------
	template
--------------------------------------------------------------------------*/
<template>
  <div class="pointer" ref="pointer">
	</div>
</template>


/*--------------------------------------------------------------------------
	script
--------------------------------------------------------------------------*/
<script>
export default {
  props: {
    msg: String
  },

  /**
   * @created
   */
  created() {
		document.body.addEventListener("mousemove", (e)=>{
			let rect = this.$refs.pointer.getClientRects()[0];
			let x = e.pageX - rect.width / 2;
			let y = e.pageY - rect.height / 2;

			// if(document.body.clientWidth < x + rect.width){
			// 	x = document.body.clientWidth - rect.width;
			// }

			this.$refs.pointer.style.transform = `translate3d(${x}px, ${y}px, 0px)`;
		});
	},


  /**
   * @methods
   */
  methods: {
		// mousemove: (e) => {
		// 	console.log(e);
		// }
	}
}
</script>



/*--------------------------------------------------------------------------
	style
--------------------------------------------------------------------------*/
<style lang="scss">

/*
*{
	cursor: none;
}
*/



.pointer{
	position: absolute;
	top: 0;
	left: 0;
	z-index: 99999;
	pointer-events: none;
	width: 50px;
	height: 50px;
	border-radius: 100%;
	// background: rgba(#000000, 0.5);
	border: 3px solid rgba(#000000, 0.5);

	transition: 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
}


</style>
