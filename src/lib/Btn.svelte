<script>
    export let primary = true
    export let red = true
    export let text = "Default Text"
    export let corner = "none"
</script>

<button id="{primary ? 'primary-btn': 'secondary-btn'}" class="{red ? 'red': 'black'}"><div class="{corner}"><span>{text}</span></div></button>

<style>
  button{
    position: relative;
    padding: 24px;
    border-radius: 10px;
    border: none;
    overflow: hidden;
    min-width: 160px;
    background-color: transparent;
    
  }
  button.red > div{
    background-color: #EA0000;
  }
  button.black > div{
    background-color: #2A333E ;
  }
  div{
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10px;
    inset: 0;
    transform: skewX(-15deg);
    
  }
  div.right{
    transform-origin: top;
  }
  div.left{
    transform-origin: bottom;
  }
  div > span{
    display: block;
    color: white;
    transform: skewX(15deg);
  }
  #primary-btn{
    height: 65px;
    font-size: 18px;
  }
  #secondary-btn{
    height: 47px;
    overflow: inherit;
    font-size: 12px;
    font-weight: 500;
    
  }
</style>