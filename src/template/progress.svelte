<script>
import { tweened } from 'svelte/motion';
import { cubicOut } from 'svelte/easing';
let y = 0
  const progress = tweened(0, {
    duration: 1000,
	easing: cubicOut
	});
</script>
<svelte:window bind:scrollY={y}/>
<p></p>
<progress value = {y/832}></progress> 
<style>
      progress{
    display: block;
    position: fixed;
    width: 90%;
    margin-left: 5%;
    margin-right: 5%;
    height: 25px;
    top:10px;
    
  }
</style>
