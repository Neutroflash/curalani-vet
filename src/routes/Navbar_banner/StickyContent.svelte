
<script>
  import sticky from './sticky.js';

  export let stickToTop = true;

  let isStuck = false;

  function handleStuck(e) {
      isStuck = e.detail.isStuck;
  }

  function ShowSlidebar() {
      var SlideBar = document.getElementById('ShowSlidebar');
      SlideBar.style.display = 'flex';
    }
  
</script>

<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Dosis:wght@200..800&display=swap" rel="stylesheet">
</svelte:head>

<section>
  {#if !stickToTop}
      <slot />
  {/if}

  <div
      class="sticky"
      class:isStuck
      data-position={stickToTop ? 'top' : 'bottom'}
      use:sticky={{ stickToTop }}
      on:stuck={handleStuck}>
      <div class="contenedor-Navegacion flex items-center justify-between flex-row">
          <a href="/">
            <div class="conetenedor-logoAndTexto flex items-center justify-center m-1 ml-[5rem]">
              <div class="contenedor-logo w-[5.14rem] h-[5rem] mr-[0.5rem]">
              </div>
              <div class="contendor-logoTexto flex justify-start items-start flex-col">
                <span class="text-[1.5rem] m-0 underline text-[white]">
                  Clinica Veterinaria
                </span>
                <span class="text-[2rem] tracking-[0.27rem] text-[white]">
                  CURALANI
                </span>
              </div>
            </div>
          </a>
          

          <div class="contenedor-menuNavegacion flex items-center justify-end flex-row">

            <!-- NAVEGADOR RESPONSIVO -->

            <ul class="SlideBar">
              <li><a href="/"><div class="conetenedor-logoAndTexto flex items-center justify-center ml-2 mr-4 mt-4">
                <div class="contenedor-logo w-[5.14rem] h-[5rem] mr-[0.5rem]">
                </div>
                <div class="contendor-logoTexto flex justify-start items-start flex-col">
                  <span class="text-[1.5rem] m-0 underline text-[#706F6F]">
                    Clinica Veterinaria
                  </span>
                  <span class="text-[2rem] tracking-[0.27rem] text-[#706F6F]">
                    CURALANI
                  </span>
                </div>
              </div></a></li>
              <li class="texto-Navegacion text-[1.2rem] text-[#706F6F]"><a href="/">Quienes somos</a></li>
              <li class="texto-Navegacion text-[1.2rem] text-[#706F6F]"><a href="/">Nuestra Familia</a></li>
              <li class="texto-Navegacion text-[1.2rem] text-[#706F6F]"><a href="/">Especialidades</a></li>
              <li class="texto-Navegacion text-[1.2rem] text-[#706F6F]"><a href="/">Servicios</a></li>
            </ul>

            <!-- NAVEGADOR ESCRITORIO -->

            <ul class="flex justify-center items-center flex-row gap-24 mr-[5rem] ">
              <li class="aea text-[1.2rem] text-[white]"><a href="#QuienesSomos">Quienes somos</a></li>
              <li class="text-[1.2rem] text-[white]"><a href="/">Nuestra Familia</a></li>
              <li class="text-[1.2rem] text-[white]"><a href="/">Especialidades</a></li>
              <li class="text-[1.2rem] text-[white]"><a href="/">Servicios</a></li>
              <button onclick=ShowSlidebar()><svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960" width="24px" fill="#e8eaed"><path d="M120-240v-80h720v80H120Zm0-200v-80h720v80H120Zm0-200v-80h720v80H120Z"/></svg></button>
            </ul>
          </div>
        </div>
      </div>

  {#if stickToTop}
      <slot />
  {/if}
</section>


<style>

  .sticky {
        position: sticky;
        background: transparent;
        transition: all 0.3s;
        margin: 0;
    }
  
    .sticky[data-position='top'] {
        top: 0rem;
    }
  
    .sticky[data-position='bottom'] {
    margin: 0;
    }
  
    .sticky.isStuck {
        background: white;
        box-shadow: 0px 0px 1px 0px rgba(0, 0, 0, 0.2),
            0px 0px 6px 0px rgba(0, 0, 0, 0.3);
            z-index: 999;
            width: 100%;
    }
  
    .sticky.isStuck li{
        color: #706F6F;
    }
  
    .sticky.isStuck li:hover{
        color: rgb(208, 56, 1);
    }
  
    .sticky.isStuck span{
        color: #706F6F;
    }

    .SlideBar .contenedor-logo{
      background-image: url('https://res.cloudinary.com/dfjn83ofc/image/upload/v1720813943/LOGO_ol4bix.png');
      margin: 0rem;
    }
  
    .contenedor-logo{
        background-image: url('https://res.cloudinary.com/dfjn83ofc/image/upload/v1720821305/Logo_blanco_yvzri7.png');
        background-size: cover;
        background-repeat: no repeat;
        background-position: center center;
    }
  
    .sticky.isStuck .contenedor-logo{
        background-image: url('https://res.cloudinary.com/dfjn83ofc/image/upload/v1720813943/LOGO_ol4bix.png');
        background-size: cover;
        background-repeat: no repeat;
        background-position: center center;;
    }
  
    span{
      line-height: 1.7rem;
    }
    
    li:hover{
      color: rgb(208, 56, 1);
    }

    .SlideBar{
        position: fixed;
        top: 0;
        right: 0;
        height: 100vh;
        width: 19rem;
        z-index: 999;
        background-color: rgba(255,255,255,0.2);
        backdrop-filter: blur(10px);
        box-shadow: -10px 0 10px rgba(0,0,0,0.1);
        display: none;
        flex-direction: column;
        justify-content: flex-start;
        align-items: flex-start;
    }

    .SlideBar .texto-Navegacion{
      width: 100%;
      margin-top: 3rem;
      margin-left: 2rem;
    }

    .SlideBar a{
      width: 100%;
    }

  </style>