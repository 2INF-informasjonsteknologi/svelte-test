<script>
  let temperature = 0;
  let showFire = false;

  // Update showFire whenever temperature changes
  $: showFire = temperature >= 10;

  function increaseTemperature() {
    temperature++;
  }

  function decreaseTemperature() {
    if (temperature > 0) {
      temperature--;
    }
  }
</script>

<div id="app">
  <h1>Ovn Temperatur</h1>
  <div class="temperature">
    <button on:click={decreaseTemperature}>-</button>
    <span>{temperature} °C</span>
    <button on:click={increaseTemperature}>+</button>
  </div>
</div>

<div class="oven">
  <div class="back"></div>
  <div class="top_holder"><div class="top"></div></div>
  <div class="front">
    <div class="knob_row">
      <div class="three_knob_holder">
        <span class="circle_knob"><span class="center"></span></span>
        <span class="circle_knob"><span class="center"></span></span>
      </div>
      <div class="three_knob_holder">
        <span class="circle_knob"><span class="center"></span></span>
        <span class="circle_knob"><span class="center"></span></span>
      </div>
    </div>
    <div class="door">
      <div class="knob">
        <div class="left"></div>
        <div class="center"></div>
        <div class="right"></div>
      </div>
      <div class="glass">
        <div class="fire">
          <div class="fire-left">
            <div class="main-fire"></div>
            <div class="particle-fire"></div>
          </div>
          <div class="fire-main">
            <div class="main-fire"></div>
            <div class="particle-fire"></div>
          </div>
          <div class="fire-right">
            <div class="main-fire"></div>
            <div class="particle-fire"></div>
          </div>
          <div class="fire-bottom">
            <div class="main-fire"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="legs_holder"></div>
</div>

<style>
  @import "../lib/style.css";
  @import "../lib/fire.css";

  #app {
    text-align: center;
    padding: 20px;
  }

  .temperature {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  span {
    font-size: 35px;
    margin: 0 20px;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  }

  button {
    padding: 20px 40px;
    margin: 0 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    background-color: #000000;
    color: #fff;
  }

  button:hover {
    background-color: #3a3a3a;
  }
</style>
