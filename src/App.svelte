<script>
  import Btn from './lib/Btn.svelte';
  import Nav from './lib/Nav.svelte'
  import Map from './lib/Map.svelte'
  import StarRating from 'svelte-star-rating';
  import Saos from "saos";

  const populars = [
    {
      title: "Kebab d'agneau (Adana Kebap)",
      rating: 4.5,
      origin: "Le kebab d'agneau est l'une des spécialités les plus emblématiques de la cuisine turque. Il est préparé avec de la viande d'agneau hachée, assaisonnée avec des épices locales, puis grillée sur une broche. Il est généralement servi avec du pain pita (lavash) et des garnitures telles que des oignons, des tomates et des piments. Un incontournable pour les amateurs de viande.",
      price: 14.00,
      img: '/assets/dish/turkish-arabic-traditional-ramadan-mix-kebab-plate-kebab-adana-chicken-lamb-beef-lavash-bread-with-sauce-top-view.jpg'
    },
    {
      title: 'Dolma',
      rating: 4.9,
      origin: "Le dolma est un plat traditionnel turc composé de légumes (comme les poivrons, les tomates ou les aubergines) farcis avec un mélange de riz, de viande hachée, d'oignons et d'épices. Les légumes farcis sont cuits dans une sauce tomate, créant un plat délicieusement savoureux et coloré.",
      price: 22.00,
      img: '/assets/dish/leaf-dolma-with-meat-table.jpg'
    },
    {
      title: 'Manti',
      rating: 5,
      origin: "Le manti est un plat turc semblable à des raviolis. Il est composé de petites pâtes farcies de viande hachée, d'oignons et d'épices. Les petits raviolis sont ensuite cuits à la vapeur ou bouillis et servis avec une sauce à base de yaourt, d'ail et de beurre fondu. Le résultat est une combinaison de saveurs délicates.",
      price: 19.00,
      img: '/assets/dish/georgian-khinkali-held-by-fork.jpg'
    },
    {
      title: 'Iskender Kebab',
      rating: 4.4,
      origin: "L'Iskender Kebab est une délicieuse création turque composée de fines tranches de viande d'agneau rôti, servies sur un lit de pain pita grillé. La viande est traditionnellement nappée d'une sauce tomate riche et de yaourt, puis accompagnée de beurre fondu et de morceaux de pita croustillants. Ce plat est généralement servi avec des légumes grillés ou des tomates rôties. C'est un incontournable pour les amateurs de viande et de saveurs complexes.",
      price: 16.00,
      img: '/assets/dish/skenderkebab-min.jpg'
    }
  ]

  const menuTurc = {
  entrees: [
    {
      nom: "Börek",
      description: "Feuilletés au fromage ou à la viande",
      prix: 5.50,
    },
    {
      nom: "Cacık",
      description: "Yaourt à la concombre et à la menthe",
      prix: 4.00,
    },
    {
      nom: "Dolma",
      description: "Feuilles de vigne farcies à la viande ou aux légumes",
      prix: 6.20,
    },
    {
      nom: "Mercimek Çorbası",
      description: "Soupe de lentilles",
      prix: 4.80,
    },
  ],
  plats: [
    {
      nom: "Kebab",
      description: "Viande grillée servie avec du riz et des légumes",
      prix: 12.50,
    },
    {
      nom: "Iskender",
      description: "Kebab servi sur du pain turc avec sauce tomate et yaourt",
      prix: 14.00,
    },
    {
      nom: "Moussaka",
      description: "Plat à base d'aubergines, viande hachée et sauce béchamel",
      prix: 10.80,
    },
    {
      nom: "Mantı",
      description: "Raviolis turcs servis avec du yaourt et du beurre",
      prix: 11.00,
    },
  ],
  desserts: [
    {
      nom: "Baklava",
      description: "Pâtisserie aux noix et au miel",
      prix: 6.00,
    },
    {
      nom: "Kadayıf",
      description: "Pâtisserie aux fils de cheveux, noix et sirop sucré",
      prix: 5.50,
    },
    {
      nom: "Sütlaç",
      description: "Riz au lait à la cannelle",
      prix: 4.50,
    },
    {
      nom: "Revani",
      description: "Gâteau de semoule imbibé de sirop",
      prix: 5.20,
    },
  ],
  boissons: [
    {
      nom: "Ayran",
      description: "Boisson au yaourt salée et rafraîchissante",
      prix: 2.50,
    },
    {
      nom: "Şalgam Suyu",
      description: "Jus de légumes fermenté, typique d'Adana",
      prix: 3.20,
    },
    {
      nom: "Turkish Coffee",
      description: "Café turc traditionnel",
      prix: 4.00,
    },
    {
      nom: "Salep",
      description: "Boisson chaude à base d'orchidée et d'épices",
      prix: 4.50,
    },
    {
      nom: "Soda 33cl",
      description: "Coca, Ice-tea ...",
      prix: 2.50,
    },
  ],
  };
  let menuToDisplay = 'entrees'

  const selectItems = (item) => {
      menuToDisplay = item
    }

  const config = {
    emptyColor: '#E4E4E4',
    fullColor: '#EA0000',
    showText: false,
    size: 15,
  };

  
</script>
<header class="wrap small">
  <Nav/>
  <Saos animation={'fade-in 1.2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}
  animation_out={'slide-out-fwd-center 0.7s cubic-bezier(0.550, 0.085, 0.680, 0.530) both'}
  top={250}
  bottom={0}>
  <div class="intro-container">
    <div class="suggestions">
      <p class="title-label">Le meilleur de la restauration turc</p>
      <h1 class="suggestion-title">kebap</h1>
      <p class="suggestion-description">Une viande de volaile grillé accompagné d'une sauce au choix, souvent accompagné d'une delicieuse sauce maison au Yaourt préparé suivant les standards ... ça vous tente ? </p>
      <div class="intro-dish-resp">
        <img src="/assets/decor/HeroImage.png" alt="">
      </div>
      <div class="btn-container">
        <Btn primary red corner="right" text="Menu"/>
        <Btn primary red={false} corner="left" text="Réserver une table"/>
      </div>
      <div class="schedule-block">
        <div>
          <p>Déjeuner</p>
          <p>10h30-15h00</p>
        </div>
        <div>
          <p>Dinner</p>
          <p>18h-23h</p>
        </div>
      </div>
    </div>
</div>
<div class="intro-dish">
  <img src="/assets/decor/HeroImage.png" alt="">
</div>
</Saos>
</header>
<main class="">
  <section id="store">
    <div class="wrap large">
  <Saos animation={'fade-in 1.2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}
  animation_out={'slide-out-fwd-center 0.7s cubic-bezier(0.550, 0.085, 0.680, 0.530) both'}
  top={250}
  bottom={250}>
    <div class="sec-title">
      <p class="display2label">Nos plats populaires</p>
      <h2>Assiette</h2>
    </div>
  </Saos>
  <Saos animation={'fade-in 1.2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}
  animation_out={'slide-out-fwd-center 0.7s cubic-bezier(0.550, 0.085, 0.680, 0.530) both'}
  top={250}
  bottom={250}>
    <div class="products-container">
      {#each populars as product}
        <div class="basic-card">
          <div class="card-head">
            <div class="img-container">
              <img src="{product.img}" alt="">
            </div>
            <div class="card-head-text">
              <p class="product-title">{product.title}</p>
              <div class="review">
                <StarRating rating={product.rating} {config} style="display: inline, margin-bottom: 25px"/>
              </div>
            </div>
          </div>
            <p class="origin">{product.origin}</p>
            <!-- <div class="btn-ctn">
              <Btn primary={false} red text={"Prix" + ' ' + product.price + ' €'}/>
            </div> -->
        </div>
      {/each}
    </div>
    <div class="center-btn">
      <Btn primary={false} red text="Nous contacter"/>
    </div>
    </Saos>
  </div>  
  </section>
  <section class="menu" id="menu">
    <div class="wrap small">
      <h2>Notre &#160 menu</h2>
      <div class="menu-container">
        <div class="head-menu">
          {#each Object.entries(menuTurc) as [key, value], index (key)}
            <button class={menuToDisplay === key ? 'selected menu-btn': 'menu-btn'} on:click={() => selectItems(key)}>{key}</button>
          {/each}
          </div>
          <div class="">
            {#each Object.entries(menuTurc[menuToDisplay]) as [index, entree]}
            <div class="body-menu"> 
              <p>{entree.nom}</p>
              <p style="font-weight: 400;">{entree.description}</p>
              <p>{entree.prix} €</p>
            </div>
            {/each}
        </div>
      </div>
    </div>
  </section>
  <section id="about">
    <div class="wrap small">
        <div class="about-us">
          <div>
          <h2>A &#160 propos &#160 de &#160 nous</h2>
          <p style="margin-bottom: 24px;">Nous sommes Emre et Fatma, et nous avons créer le restaurant Yannal en 2017, originaire de turquie, nous nous sommes pris pour passion la cuisine de nos parents, et nous vous proposons une mutlitude de plats, préparé maisons, avec amour.</p>
            <Btn primary={false} red text="Nous contacter"/>
          </div>
          <div class="container-img-about">
            <img src="/assets/us.webp" alt="">
          </div>
        </div>
    </div>
  </section>
  <section id="location">
    <div class="wrap large">
      <h2>Adresse</h2>
      <p>Nous nous situons au : 8 rue perle, Schiltigheim, 67300</p>
      <Map/>
    </div>
  </section>

</main>
<footer class="wrap large">
</footer>

<style>
  .about-us{
    display: flex;
    gap: 48px;
  }
  .container-img-about{
    max-width: 420px;
    filter: drop-shadow(0px 100px 80px rgba(0, 0, 0, 0.07)) drop-shadow(0px 64.8148px 46.8519px rgba(0, 0, 0, 0.0531481)) drop-shadow(0px 38.5185px 25.4815px rgba(0, 0, 0, 0.0425185)) drop-shadow(0px 20px 13px rgba(0, 0, 0, 0.035)) drop-shadow(0px 8.14815px 6.51852px rgba(0, 0, 0, 0.0274815)) drop-shadow(0px 1.85185px 3.14815px rgba(0, 0, 0, 0.0168519));
  }
  .container-img-about img{
    width: 100%;
    object-fit: cover;
  }
  .body-menu{
    display: grid;
    grid-template-columns: 15% 75% 10%;
    padding: 8px 0;
    border-bottom: 2px solid #2A333E;
    align-items: center;
  }
  .head-menu{
    text-align: center;
    display: flex;
    /* justify-content: center; */
    gap: 6px;
    margin-bottom: 24px;
    flex-wrap: wrap;
  }
  .menu-btn{
    padding: 8px;
    background-color: #2A333E;
    border: none;
    border-radius: 4px;
    color:white;
  }
  .menu-btn.selected{
    background-color: #EA0000;
  }

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
    margin-top: -135px;
    padding-top: 203px;
    padding-bottom: 68px;
  }
  section#menu{
    position: relative;
  }
  .products-container{
    margin-top: 110px;
    display: grid;
    /* grid-template-columns: repeat(2, minmax(218px, 1fr)); */
    grid-template-columns: repeat( auto-fit, minmax(351px, 1fr) );
    gap: 60px;
  }
  .basic-card{
    display: flex;
    flex-direction: column;
  }
  .center-btn{
    margin-top: 48px;
    text-align: center;
  }
  .btn-ctn{
    flex: 1;
    display: flex;
    align-items: flex-end;
    margin-top: 8px;
  }
  .card-head{
    display: flex;
    gap: 24px;
  }
  .card-head-text{
    flex: 1;
    align-items: center;
  }
  .img-container{
    width: 180px;
    margin-bottom: 38px ;
    height: 180px;
    border-radius: 999px;
    overflow: hidden;
    filter: drop-shadow(0px 100px 80px rgba(0, 0, 0, 0.07)) drop-shadow(0px 64.8148px 46.8519px rgba(0, 0, 0, 0.0531481)) drop-shadow(0px 38.5185px 25.4815px rgba(0, 0, 0, 0.0425185)) drop-shadow(0px 20px 13px rgba(0, 0, 0, 0.035)) drop-shadow(0px 8.14815px 6.51852px rgba(0, 0, 0, 0.0274815)) drop-shadow(0px 1.85185px 3.14815px rgba(0, 0, 0, 0.0168519));
  }
  .img-container img{
    object-fit: cover;
    width: 100%;
    height: 100%;
    object-position: bottom;
  }
  .origin{
    font-weight: 400;
    font-size: 15px;
    line-height: 22px;
  }
  .product-title{
    margin-top: 16px;
    margin-bottom: 16px;
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
    /* .products-container{
      grid-template-columns: repeat(auto-fill, minmax(min-content, 1fr));
      row-gap: 42px;
      column-gap: 42px;
    } */
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
    .body-menu{
      grid-template-columns: 75% 25%;
      grid-template-rows: auto;
    }
    .body-menu p:last-child{
      grid-column: 2;
      grid-row: span 2;
      text-align: center;
    }
    .body-menu p:nth-child(2){
      grid-row: 2
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
