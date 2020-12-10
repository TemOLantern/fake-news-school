<script>
import Switch2 from './switch2.svelte'
import { fly } from 'svelte/transition'
import Switch from './switch.svelte';
let darkmode
</script>
<div class="settings" transition:fly="{{ y: -10, duration: 100}}">
    <h1>Innstillinger:</h1>
    <span class="underline"/>
    <div class="darkmode">
    <p>Dark mode:</p>
    <Switch bind:checked={darkmode}></Switch>
    </div>
    <div class="gifdisable">
    <Switch2></Switch2>
    <p>Disable gif:</p>
    </div>
</div>
<style>
.darkmode{
    padding: 10px;
    margin-top: 20px;
    display: block;
}
.gifdisable{
    padding: 10px;
    margin-top: 40px;
}
    .underline{
border-bottom: 1px dotted black;
width: 100%;
display: block;
}
    .settings{
    color: white;
    background-color: grey;
    border: 2px solid black;
    border-radius: 10px;
    position: fixed;
    z-index: 100;
    margin-right: auto;
    margin-left: auto;
    top:30%;
    left:27%;
    padding: 50px;
    width: 600px;
    padding-top:20px
}
.settings p {
    margin: 0px;
    float: left;
    font-size: 40px;
    margin-top: 0px;
}
.settings h1{
    text-align: center;
    font-size: 40px;
    margin: 5px;
}

</style>
