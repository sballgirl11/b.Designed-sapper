<script>
  import { fly } from "svelte/transition";
</script>

<svelte:head>
  <title>About</title>
</svelte:head>

<div in:fly={{ x: -200, duration: 700 }}>

  <h1>About b.Designed</h1>

  <div class="top">
    <img src="family.jpg" alt="my family" class="family" />
    <p>
      I am a mom of 3 wonderful children and we live in the beautiful city of
      Holland, Michigan. I love developing web sites that are beautiful, that
      are also fluid, responsive, and easy to use. I thrive on mobile-first
      development with an extensive knowledge of CSS and React with Gatsby,
      Svelte with Sapper, SEO, UX/UI design, and logo design. I love learning
      about all the cool new stuff that comes out in the tech world daily. I
      also 💖 coffee and beer 🍻, well because mom life!
    </p>
  </div>

  <hr />
  <div class="skills-cont">

    <h1>Skills</h1>

    <div class="bottom">

      <div class="card-container">
        <div class="card">
          <div class="side">
            <img src="/icons/webdev.png" alt="web dev" class="icons-top" />
          </div>
          <div class="side back">
            Web
            <br />
            Development
          </div>
        </div>
      </div>

      <div class="card-container">
        <div class="card">
          <div class="side">
            <img src="/icons/marketing.png" alt="marketer" class="icons-top" />
          </div>
          <div class="side back">Marketing</div>
        </div>
      </div>

      <div class="card-container">
        <div class="card">
          <div class="side">
            <img
              src="/icons/graphic.png"
              alt="graphic designer"
              class="icons-top" />
          </div>
          <div class="side back">
            Graphic
            <br />
            Design
          </div>
        </div>
      </div>

      <div class="card-container">
        <div class="card">
          <div class="side">
            <img src="/icons/fast.png" alt="fast" class="icons-bottom" />
          </div>
          <div class="side back">Fast</div>
        </div>
      </div>
      <div class="card-container">
        <div class="card">
          <div class="side">
            <img
              src="/icons/responsive.png"
              alt="responsive"
              class="icons-bottom" />
          </div>
          <div class="side back">Responsive</div>
        </div>
      </div>
      <div class="card-container">
        <div class="card">
          <div class="side">
            <img
              src="/icons/intuitive.png"
              alt="intuitive"
              class="icons-bottom" />
          </div>
          <div class="side back">Intuitive</div>
        </div>
      </div>
      <div class="card-container">
        <div class="card">
          <div class="side">
            <img src="/icons/dynamic.png" alt="dynamic" class="icons-bottom" />
          </div>
          <div class="side back">Dynamic</div>
        </div>
      </div>
    </div>
  </div>
</div>

<style>
  h1 {
    letter-spacing: 0.2em;
  }

  p {
    font-size: 3vh;
    text-shadow: 2px 2px 1px black;
  }

  hr {
    margin: 3em auto;
    width: 75%;
  }

  .top {
    margin: 0 auto;
    width: 75%;
    display: grid;
    grid-template-columns: 1fr 2fr;
    grid-gap: 4em;
    align-items: center;
    justify-content: center;
  }

  .bottom {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    grid-gap: 2em;
    justify-content: center;
    justify-items: center;
    width: 75%;
    margin: 2em auto;
    padding: 1em;
  }

  .family {
    width: 75%;
    transform: rotate(-15deg);
  }

  .skills-cont {
    margin-top: -25px;
  }

  .skills-cont > h1 {
    margin-bottom: -25px;
  }

  .card-container {
    height: 150px;
    position: relative;
    width: 150px;
  }

  .card {
    height: 100%;
    transform-style: preserve-3d;
    transition: all 1s ease-in-out;
    position: absolute;
    width: 100%;
    border-radius: 25%;
    border: 5px solid rgb(241, 241, 241);
    background-color: rgb(241, 241, 241);
    box-shadow: 0 4px 8px 0 rgb(34, 34, 34, 0.808);
    color: #111;
  }

  .card-container > .card:hover {
    transform: rotateY(180deg);
  }

  .card .side {
    -ms-perspective: 0;
    -ms-backface-visibility: hidden;
    -ms-transform: translate3d(0, 0, 0);
    perspective: 0;
    transform: translate3d(0, 0, 0);
    -webkit-perspective: 0;
    -webkit-backface-visibility: hidden;
    -webkit-transform: translate3d(0, 0, 0);
    visibility: visible;
    backface-visibility: hidden;
    height: 100%;
    position: absolute;
    width: 100%;
  }

  .card .back {
    -ms-perspective: 0;
    -ms-backface-visibility: hidden;
    -ms-transform: translate3d(0, 0, 0);
    perspective: 0;
    transform: translate3d(0, 0, 0);
    -webkit-perspective: 0;
    -webkit-backface-visibility: hidden;
    -webkit-transform: translate3d(0, 0, 0);
    visibility: visible;
    backface-visibility: hidden;
    color: black;
    font-size: 2vh;
    font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
    font-style: italic;
    transform: rotateY(180deg);
  }

  .side {
    display: grid;
    justify-content: center;
    align-items: center;
    position: relative;
    top: -2%;
    font-size: 2vh;
    text-align: center;
  }

  .icons-top {
    width: 100%;
  }

  .icons-bottom {
    width: 100%;
  }

  @media only screen and (max-width: 600px) {
    .top {
      grid-template-columns: 1fr;
      justify-items: center;
      width: 100%;
      text-align: center;
    }

    .family {
      width: 75%;
      transform: none;
    }
  }

  @media only screen and (min-width: 600px) and (max-width: 1400px) {
    .top {
      grid-template-columns: 1fr;
      justify-items: center;
      width: 100%;
      text-align: center;
    }
    .family {
      width: 50%;
      transform: none;
    }
  }

  @media only screen and (min-width: 1001px) and (max-width: 1400px) {
    .top {
      grid-template-columns: 1fr;
      justify-items: center;
      width: 100%;
      text-align: center;
    }
    .family {
      width: 35%;
      transform: none;
    }
  }
</style>
