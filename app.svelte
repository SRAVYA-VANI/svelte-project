<script>
  import Card from "./Card.svelte";
  let memes = [];
  let jokes = [];
  let info = " ";
  async function getdata() {
    const data = await fetch("https://api.covid19api.com/summary");
    const d = await data.json();
    info = d.Global;
    console.log(info);
  }
  async function getJoke() {
    const data = await fetch("https://official-joke-api.appspot.com/random_joke");
    const d = await data.json();
    console.log(d);
    jokes = d;
  }
  async function getData() {
    const data = await fetch("https://api.imgflip.com/get_memes");
    const d = await data.json();
    memes = d.data.memes;
    console.log(memes);
  }
</script>

<div>
<div class="continer">
  <marquee id="marq">Daily You can get <span style="color:red">COVID-19</span> updates by clicking the below button.It was just for information,there is no need to get afraid of <span style="color:red">COVID</span>.---STAY HOME___STAY SAFE---</marquee>
  <div>
  <button class="v"on:click={getdata}>
		COVID-19 Updates
	</button><br><br>
  <div class="covid">
    {#if info.TotalConfirmed > 1}
  <h1 class="z"><span class="cvd">Total cases</span>=<span class="res">{info.TotalConfirmed}</span></h1>
	<h1 class="e">
		<span class="cvd">Total deaths</span>=<span class="res">{info.TotalDeaths}</span>
	</h1>
	<h1 class="e">
		<span class="cvd">Total recovered</span>=<span class="res">{info.TotalRecovered}</span>
	</h1><br>
  <img class="m" src="https://www.potential.com/wp-content/uploads/2020/03/Untitled-1.jpg" alt="">
	{/if}
  </div>
</div>
  <h1 class="c">DON'T  GET PANIC FOLKS!</h1>
  <h1 class="A">STAY HOME ND HAVE FUN BY WATCHING MEMES ND JOKES :) </h1>
  <h1 class="b">ARE U READY FOR FUN :)</h1>
  <img class="d" src="https://i.kym-cdn.com/entries/icons/original/000/014/057/Screenshot_7.jpg" alt=""><br>
</div>
<div class="box">
  <button class="s" on:click={getJoke}>Get jokes</button>
  <p>----------Everytime you click's the button,You'll get a different Joke.----------</p>
  {#if jokes.setup!=undefined}
    <h1 id="jo">{jokes.setup}</h1>
    <h2 id="ke">{jokes.punchline}</h2>
  {/if}
</div>
<div class="memes">
<button class="s" on:click={getData}>Get memes</button>
 <p>----------It's memes time.Just watch and enjoyyy.----------</p>
</div>

  {#each memes as m}
   <Card name={m.name} url={m.url}/>
  {/each}
 
</div>

<style>
  .z {
    color: white;
    font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
    margin-top: 10px;
  }
  .m {
    height: 250px;
    margin: 0 auto;
    width: 350px;
    margin-bottom: 30px;
    border-radius: 20px 20px 20px;
    border: 3px solid white;
    box-shadow: 10px 10px 10px rgb(104, 102, 102);
    text-align: center;
  }
  .res {
    color: red;
    text-shadow: 2px 2px 2px black;
  }
  .cvd {
    color: white;
    text-shadow: 2px 2px 2px black;
  }
  .e {
    color: white;
    font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
  }
  .covid {
    text-align: center;
    border: 1px solid white;
    margin: 0 auto;
    width: 450px;
    border-radius: 30px 30px 30px;
  }
  .v:hover {
    box-shadow: 5px 5px 5px red;
    border: 2px double red;
  }
  .v:active {
    color: red;
    text-shadow: 2px 2px 2px #111c3a;
  }
  .v {
    padding: 5px 30px;
    align: center;
    font-size: 15px;
    font-weight: bold;
    border-radius: 5px 5px 5px;
    outline: 0;
    border: 2px solid skyblue;
    background: skyblue;
    color: #111c3a;
    cursor: pointer;
    box-shadow: 5px 5px 5px black;
  }
  #marq {
    color: white;
    font-family: sans-serif;
    font-size: 15px;
    font-weight: bold;
    margin: 10px 5px;
    text-shadow: 2px 2px 2px black;
  }
  .c {
    font-style: italic;
    color: rgb(255, 137, 2);
    font-weight: bold;
    text-shadow: 1px 1px 1px white;
    padding-top: 20px;
  }
  .s:hover {
    background: rgb(24, 6, 3);
    color: orange;
    text-shadow: 2px 2px 2px black;
    border: 3px dashed skyblue;
  }
  .s:active {
    font-size: 25px;
    height: 50px;
    width: 380px;
  }
  .memes {
    border: 5px solid hotpink;
    margin-top: 20px;
    box-shadow: 10px 10px 10px black;
    border-radius: 30px;
    background-color: #111c3a;
    margin: 0 10px;
  }
  p {
    color: white;
    font-size: 20px;
    margin-bottom: 20px;
    font-family: sans-serif;
  }
  .box {
    box-shadow: 10px 10px 10px black;
    border-radius: 30px;
    font-style: oblique;
    background-color: #111c3a;
    margin: 0 10px;
    margin-bottom: 20px;
    border: 5px solid yellow;
  }
  #jo {
    color: white;
    margin-top: 10px;
    margin-bottom: 20px;
  }
  #ke {
    color: white;
    margin-bottom: 20px;
  }
  .continer {
    background-color: #111c3a;
    border-radius: 30px;
    margin: 0 10px;
    border: 5px solid skyblue;
    margin-bottom: 20px;
    box-shadow: 10px 10px 10px black;
  }
  * {
    margin: 0;
    padding: 0;
    text-align: center;
  }

  .d {
    height: 250px;
    margin: 0 auto;
    margin-bottom: 30px;
    border-radius: 20px 20px 20px;
    border: 3px solid white;
    box-shadow: 10px 10px 10px rgb(104, 102, 102);
    text-align: center;
  }
  .A {
    font-style: italic;
    color: rgb(255, 137, 2);
    font-weight: bold;
    margin-bottom: 20px;
    text-shadow: 1px 1px 1px white;
    padding-top: 20px;
  }
  .b {
    font-style: italic;
    margin-bottom: 30px;
    color: rgb(216, 199, 49);
    text-shadow: 1px 1px 1px white;
  }
  .s {
    margin-top: 20px;
    background-color: #ffe4c4;
    font-family: "Courier New", Courier, monospace;
    font-weight: bolder;
    text-shadow: 2px 2px 2px black;
    color: rgb(228, 69, 49);
    text-align: center;
    font-size: 30px;
    border: 3px dashed rgb(65, 64, 64);
    border-radius: 20px;
    box-shadow: 5px 5px 5px grey;
    height: 50px;
    width: 400px;
    margin-bottom: 30px;
    outline: 0;
    cursor: pointer;
  }
</style>
