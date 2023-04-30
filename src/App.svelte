<script>
  import Btn from './lib/Btn.svelte';
  import Nav from './lib/Nav.svelte'
  import StarRating from 'svelte-star-rating';
  import Saos from "saos";

  const populars = [
    {
      title: 'Hot Wings',
      rating: 4.5,
      origin: 'Chinese',
      price: 14.00,
      img: '/assets/dish/Dish-1.png'
    },
    {
      title: 'Rice with Curry',
      rating: 4.9,
      origin: 'Indian Style',
      price: 22.00,
      img: '/assets/dish/Dish.png'
    },
    {
      title: 'Chapatees',
      rating: 5,
      origin: 'Pakistani Style',
      price: 19.00,
      img: '/assets/dish/Dish-2.png'
    },
    {
      title: 'SweetDish',
      rating: 4.4,
      origin: 'Western Style',
      price: 16.00,
      img: '/assets/dish/Dish-3.png'
    }
  ]
  
  const config = {
    emptyColor: '#E4E4E4',
    fullColor: '#EA0000',
    showText: false,
    size: 15,
  };

  
</script>
<Saos animation={'fade-in 1.2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}
  animation_out={'slide-out-fwd-center 0.7s cubic-bezier(0.550, 0.085, 0.680, 0.530) both'}
  top={250}
  bottom={250}>
<header class="wrap small">
  <Nav/>
  <div class="intro-container">
    <div class="suggestions">
      <p class="title-label">Now taking online ordres</p>
      <h1 class="suggestion-title">kababs</h1>
      <p class="suggestion-description">Restaurant style Yogurt Mint Sauce is delicious dip which is quick and easy to ... This is a standard Indian mint chutney served with poppadums along with mint and lemon.</p>
      <div class="intro-dish-resp">
        <img src="/assets/decor/HeroImage.png" alt="">
      </div>
      <div class="btn-container">
        <Btn primary red corner="right" text="Add To Cart"/>
        <Btn primary red={false} corner="left" text="Book A Table"/>
      </div>
      <div class="schedule-block">
        <div>
          <p>Lunch</p>
          <p>1:00-03:00pm</p>
        </div>
        <div>
          <p>Dinner</p>
          <p>7:00-10:00pm</p>
        </div>
      </div>
    </div>
</div>
<div class="intro-dish">
  <img src="/assets/decor/HeroImage.png" alt="">
</div>
</header>
</Saos>
<main class="">
  <section id="store">
    <div class="wrap large">
  <Saos animation={'fade-in 1.2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}
  animation_out={'slide-out-fwd-center 0.7s cubic-bezier(0.550, 0.085, 0.680, 0.530) both'}
  top={250}
  bottom={250}>
    <div class="sec-title">
      <p class="display2label">online store</p>
      <h2>Popular Products</h2>
    </div>
  </Saos>
  <Saos animation={'fade-in 1.2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}
  animation_out={'slide-out-fwd-center 0.7s cubic-bezier(0.550, 0.085, 0.680, 0.530) both'}
  top={250}
  bottom={250}>
    <div class="products-container">
      {#each populars as product}
      <div class="basic-card">
        <div class="img-container">
          <img src="{product.img}" alt="">
        </div>
        <div class="review">
          <StarRating rating={product.rating} {config} style="display: inline, margin-bottom: 25px"/>
        </div>
        <p class="origin">{product.origin}</p>
        <p class="product-title">{product.title}</p>
        <Btn primary={false} red text={"Add to Cart " + ' ' + " $"+ product.price}/>
      </div>
      
      {/each}
    </div>
    </Saos>
  </div>  
  </section>
</main>
<footer class="wrap large">
</footer>

<style>
    @keyframes -global-fade-in {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }
    @keyframes -global-slide-out-fwd-center {
    0% {
      transform: translateZ(1);
      opacity: 1;
    }
    100% {
      transform: translateZ(600px);
      opacity: 0;
    }
  }
  header{
    height: 990px;
  }
  .intro-dish-resp{
    display: none;
    
  }
  section{
    background: #F9F9FB;
    padding: 68px 0;
  }
  .products-container{
    margin-top: 110px;
    display: grid;
    grid-template-columns: repeat(4, minmax(218px, 1fr));
    grid-column-gap: 110px;
  }
  .products-container > div{
    display: flex;
    flex-direction: column;
    align-items:center ;
    text-align: center;
  }
  .img-container{
    width: 180px;
    margin-bottom: 38px ;
    height: 180px;
    filter: drop-shadow(0px 100px 80px rgba(0, 0, 0, 0.07)) drop-shadow(0px 64.8148px 46.8519px rgba(0, 0, 0, 0.0531481)) drop-shadow(0px 38.5185px 25.4815px rgba(0, 0, 0, 0.0425185)) drop-shadow(0px 20px 13px rgba(0, 0, 0, 0.035)) drop-shadow(0px 8.14815px 6.51852px rgba(0, 0, 0, 0.0274815)) drop-shadow(0px 1.85185px 3.14815px rgba(0, 0, 0, 0.0168519));
  }
  .img-container img{
    object-fit: cover;
    width: 100%;
    height: 100%;
  }
  .origin{
    font-weight: 400;
    font-size: 15px;
    line-height: 22px;
  }
  .product-title{
    margin-top: 16px;
    margin-bottom: 45px;
    font-weight: 700;
    font-size: 28px;
    line-height: 42px;
  }
  .sec-title{
    text-align: center;
  }
  .schedule-block{
    margin-top: 130px;
    display: flex;
    gap: 82px;
  }
  .schedule-block > div > p:first-child{
    font-weight: 700;
    font-size: 24px;
  }
  .schedule-block > div > p:last-child{
    font-weight: 500;
    opacity: 0.5;
    font-size: 20px;
  }
  .btn-container{
    margin-top: 87px;
  }
  .title-label{
    line-height: 28px;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: #EA0000;
    font-weight: 500;
    margin-bottom: 43px;
  }
  .suggestion-description{
    max-width: 476px;
    margin-top: 32px;
    font-size: 20px;
  }
  .intro-dish{
    position: absolute;
    top: 34px;
    right: 200px;
    width: 880px;
    height: 917px;
    z-index: -1;
    transition: right, top 0.1s ease-in-out; /* transition pour un déplacement fluide */
  }
  
  .intro-dish img{
    object-fit: cover;
    width: 100%;
    height: 100%;
  }
  .suggestions{
    display: block;
    max-width: 698px;
    margin-left: 58px;
    margin-top: 152px;
  }
  /* Media query pour ajuster la position de l'image */
  @media (max-width: 1440px) {
    .intro-dish {
      right: 0; /* position finale de l'image */
    }
    .products-container{
      grid-template-columns: repeat(auto-fill, minmax(202px, 1fr));
      row-gap: 42px;
      column-gap: 42px;
    }
  }
  @media (min-width: 1100px) and (max-width: 1280px) {
  .intro-dish{
    width: 620px;
    height: auto;
    top: 50%;
    transform: translateY(-50%);
  }
  }
  @media (max-width : 1100px){
    header{
      height: 100%;
    }
    .suggestions{
      margin-left: auto;
      margin-right: auto;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .suggestion-description{
      max-width: 100%;
    }
    .intro-dish{
      display: none;
    }
    .intro-dish-resp{
      margin-top: 18px;
      width: 100%;
      height: 300px;
      display: block;
    }
    .intro-dish-resp img{
      width: 100%;
      height: 100%;
      object-fit: contain;
    }
    .btn-container{
      margin-top: 42px;
    }
  }
  @media (max-width : 768px){
    .suggestions{
      margin-top: 48px;
    }

  }
  @media (max-width: 420px){
    .btn-container{
      justify-content: center;
      row-gap: 14px;
      display: flex;
      flex-wrap: wrap;
    }
  }

</style>
