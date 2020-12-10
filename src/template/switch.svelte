<script>
    import { bool } from '../store/store.js'
    let checked
    export const color = "#2196F3";

  function check(){
    bool.update(bool => !bool)
    console.log(bool)
  }
  </script>
  
  <style>
    .switch {
      margin-top: 5px;
      position: relative;
      width: 90px;
      height: 50px;
      float: right;
    }
  
    .switch input {
      opacity: 0;
      width: 0;
      height: 0;
    }
  
    .slider {
      position: absolute;
      cursor: pointer;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background-color: #ccc;
      -webkit-transition: 0.4s;
      transition: 0.4s;
      border-radius: 34px;
    }
  
    .slider:before {
      position: absolute;
      content: "";
      height: 40px;
      width: 40px;
      left: 4px;
      bottom: 4px;
      background-color: white;
      -webkit-transition: 0.4s;
      transition: 0.4s;
      border-radius: 50%;
    }
  
    input:checked + .slider {
      background-color: #2196f3;
    }
  
    input:checked + .slider {
      box-shadow: 0 0 1px #2196f3;
    }
  
    input:checked + .slider:before {
      -webkit-transform: translateX(26px);
      -ms-transform: translateX(26px);
      transform: translateX(42px);
    }
  </style>
  
  <label class="switch">
    <input type="checkbox" bind:checked={$bool} on:click={check}/>
    <span class="slider" />
  </label>