<script>
     export let name = "";
     export let url = "";
</script>
<div>
    <img id="image" src = {url} alt = ""/>
    <h1>{name}</h1>
</div>
<style>
  #image {
    height: 430px;
    width: 370px;
    margin: 10px;
    border: 5px dotted white;
    border-radius: 30px 30px 30px;
    box-shadow: 10px 10px 10px black;
  }
  h1 {
    color: white;
    font-style: oblique;
    font-size: 40px;
    margin: 0 80px;
    border: 2px solid white;
    border-radius: 20px 20px 20px;
    box-shadow: 10px 10px 10px grey;
  }
  div {
    background-color: #111c3a;
    border-radius: 30px 30px;
    padding-top: 40px;
    text-align: center;
    margin: 30px 10px;
    height: 625px;
    border: 5px solid hotpink;
    box-shadow: 10px 10px 10px black;
  }
</style>
