<script>
  import { Router, Link, Route } from "svelte-routing";
  import Home from './sider/home.svelte';
  import Progress from './template/progress.svelte'
  import Cyber from './sider/cyber.svelte';
  import Hacking from './sider/hacking.svelte';
  import Troll from './sider/troll.svelte';
  import Fakenews from "./sider/fakenews.svelte";
  import { fly } from 'svelte/transition';
  import { fade } from 'svelte/transition';
  import Settings from './template/settings.svelte';
  import { bool } from './store/store.js';

  let bckclr
  let bck = "linear-gradient(90deg, transparent 79px, #abced4 79px, #abced4 81px, transparent 81px), linear-gradient(#eee .1em, transparent .1em);"
  let color = "white";
  let y
  let offset = 0
  let tolerance = 0
  let dropdown = false
  let navdown = true
  let lastY = 0;

  // Dark mode
  
  $: if($bool){
    color = "white";
    bckclr = "black"
    console.log(bck)
  }else{
    color = "black"
    bckclr = "white"
  }

  // Finne scroll speed
    function deriveClass(y, dy) {
      if (y < offset) {
        return true
      }
      if (Math.abs(dy) <= tolerance) {
        return headerClass;
      }
      if (dy < 0) {
        return true
      }
      return false
    }
    function updateClass(y) {
      const dy = lastY - y;
      lastY = y;
      return deriveClass(y, dy);
    }
  function onClick(){
      dropdown = false
  }
  $: navdown = updateClass(y);
  function onSettingsClick(){
      dropdown = !dropdown
  }
  
  </script>
  <svelte:window bind:scrollY = {y}/>
  <Progress/>
  <Router url="/">
    
  {#if !navdown}
    <div class="navbar" transition:fly="{{ y: -150, duration: 400}}">
      <tr>
        <Link to="/"><th>Home</th></Link>
        <Link to="fakenews"><th>Fake News</th></Link>
        <Link to="cybermobbing"><th>Cybermobbing</th></Link>
        <Link to="trollfabrikk"><th>Trollfabrikker</th></Link>
        <Link to="hacking"><th>Hacking</th></Link>
        <div on:click|stopPropagation={onSettingsClick} class="icon">
          <th id="right">⚙️</th>
        </div>
      </tr>
    </div>
  {/if}

  <div class="main" style="--color: {color}; --bckclr: {bckclr}">
  <Route path="fakenews" component="{Fakenews}" />
  <Route path="cybermobbing" component="{Cyber}" />
  <Route path="trollfabrikk" component="{Troll}" />
  <Route path="hacking" component="{Hacking}" />
  <Route path="/" component={Home}/>
  </div>

</Router>
  {#if dropdown }
   <Settings></Settings>
   <div class="darkbck" on:click={onClick} transition:fade></div>
  {/if}
  <img alt = "pog" src="https://cdn.discordapp.com/attachments/690352706635956325/786544969020080128/fake_news.png"/>
  <footer class="footer">
    
    <p>Laget av Faban Ø. Tang<br><br>For IT prosjekt desember 2020.</p>
    
  </footer>
  <style>
    img{
      position: fixed;
      height: 150px;
      left: 81%;
      top: 80%;
    }
    .footer p{
      text-align: center;
      line-height: 0.8;
      text-shadow: 1px 1px black;
    }
    footer{
      background-color: black;
      color: white;
      width: 105%;
      margin-left: -50px;
      padding:40px;
      margin-top: 200px;
      background: linear-gradient(#56565600, #000000);
    }
  .darkbck{
      position: fixed;
      left: 0;
      top: 0;
      z-index: 10;
      width: 100%;
      height: 100%;
      background-color: black;
      opacity: 0.5;
  }
  
  .icon{
      float:right;
  }
  .main{
        margin-top: 150px;
        color: var(--color);
        width: 60%;
        margin-left: 15%;
        margin-right: 20%;
        border: 4px solid black;
        border-radius: 25px;
        padding: 20px;
        padding-left: 90px;
        padding-top: 0px;
        font-size: 40px;
        background-color: var(--bckclr);
        background-image: 
        linear-gradient(90deg, transparent 79px, #abced4 79px, #abced4 81px, transparent 81px),
        linear-gradient(#eee .1em, transparent .1em);;
        background-size: 100% 1.2em;
  }
  .main:link{
    text-decoration: none;
  }
  
  .navbar{
      display: block;
      position: fixed;
      font-size: xx-large;
      background-color: #565656;
      border: 2px solid black;
      width: 97%;
      color: white;
      padding: 10px;
      border-radius: 25px;
      top: 45px;
    }
    .navbar th{
      color: white;
      margin-left: 50px;
      padding: 10px;
      cursor: pointer;
      margin: 10px;
    }
    .navbar #right{
        text-align: right;
    }
    .navbar th:hover{
      background-color: black;
      border-radius: 15px;
      scale: 1.2;
    }
    :global(a:hover){
      text-decoration: none;
    }
  </style>
  