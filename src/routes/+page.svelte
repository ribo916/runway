<script>
  let isMenuOpen = false;
  let showWhyModal = false;

  const toggleMenu = () => {
    isMenuOpen = !isMenuOpen;
  };

  const toggleWhyModal = () => {
    showWhyModal = !showWhyModal;
  };
</script>

<nav class="navbar">
  <div class="nav-brand">Rich Boesch</div>
  <button class="hamburger" on:click={toggleMenu} aria-label="Toggle menu">
    <span></span>
    <span></span>
    <span></span>
  </button>
  <div class="nav-links {isMenuOpen ? 'active' : ''}">
    <a href="https://app.enhancv.com/share/2d0c1d67/?utm_medium=growth&utm_campaign=share-resume&utm_source=dynamic" 
       target="_blank" 
       rel="noopener noreferrer">
      Resume
    </a>
    <button on:click={toggleWhyModal}>Why am I applying?</button>
  </div>
</nav>

{#if showWhyModal}
<div class="modal-overlay" 
     on:click={toggleWhyModal}
     on:keydown={(e) => e.key === 'Escape' && toggleWhyModal()}
     role="dialog"
     tabindex="0">
  <div class="modal" 
       on:click|stopPropagation 
       on:keydown={(e) => e.key === 'Escape' && toggleWhyModal()}
       role="dialog" 
       aria-modal="true" 
       tabindex="0">
    <h2>Why am I applying?</h2>
    <p>I've spent years as a developer, a dev manager, a business unit owner, a solution architect, a product owner, as well as an integration specialist. Most of my happiness comes from leveraging my technical and leadership skills with a primary focus of helping others. From the description, I am also inspired by moving away from Fintech and into a creative company focused in AI. I see this role fitting me very well, but would love to speak to you all and learn more!</p>
    <div class="button-container">
      <button class="close-button" on:click={toggleWhyModal}>Close</button>
    </div>
  </div>
</div>
{/if}

<div class="container" style="background-image: url('/resume_bg.png')">
  <div class="title-section">
    <h2>Technically fluent. Creatively curious. Always adaptable.</h2>
  </div>
  <div class="video-container">
    <iframe
      src="https://www.youtube.com/embed/sYyHPpkfij0"
      title="Application Video"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
      allowfullscreen
    ></iframe>
  </div>
</div>

<style>
  .navbar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background: rgba(255, 255, 255, 0.95);
    backdrop-filter: blur(8px);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    z-index: 1000;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  }

  .nav-brand {
    font-size: 1.5rem;
    font-weight: 600;
    color: #2c3e50;
  }

  .nav-links {
    display: flex;
    gap: 2rem;
    align-items: center;
  }

  .nav-links a, .nav-links button {
    color: #2c3e50;
    text-decoration: none;
    background: none;
    border: none;
    font-size: 1rem;
    cursor: pointer;
    padding: 0.5rem 1rem;
    border-radius: 6px;
    transition: background-color 0.3s;
  }

  .nav-links a:hover, .nav-links button:hover {
    background: rgba(44, 62, 80, 0.1);
  }

  .hamburger {
    display: none;
    flex-direction: column;
    gap: 4px;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.5rem;
  }

  .hamburger span {
    display: block;
    width: 25px;
    height: 3px;
    background: #2c3e50;
    transition: 0.3s;
  }

  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 2000;
  }

  .modal {
    background: white;
    padding: 2rem;
    border-radius: 12px;
    max-width: 500px;
    width: 90%;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }

  .container {
    padding-top: 5rem;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    border: 1px solid rgba(255, 255, 255, 0.3);
    min-width: 300px;
  }

  .title-section {
    text-align: center;
    margin-bottom: 2rem;
    color: #2c3e50;
    text-shadow: 2px 2px 4px rgba(255, 255, 255, 0.3);
    padding: 2rem 3rem;
    background: rgba(248, 250, 252, 0.97);
    backdrop-filter: blur(8px);
    border-radius: 12px;
    border: 2px solid rgba(255, 255, 255, 0.8);
    box-shadow: 
      0 15px 30px rgba(0, 0, 0, 0.15),
      0 8px 16px rgba(0, 0, 0, 0.1),
      0 0 0 1px rgba(255, 255, 255, 0.3);
    transform: translateY(10px);
  }

  h2 {
    font-size: 1.5rem;
    margin: 0;
    font-weight: 400;
    line-height: 1.4;
  }

  .video-container {
    width: 90%;
    max-width: 800px;
    aspect-ratio: 16 / 9;
    background: rgba(0, 0, 0, 0.7);
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    position: relative;
    padding: 0;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .video-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: none;
    object-fit: cover;
  }

  @media (max-width: 768px) {
    .hamburger {
      display: flex;
    }

    .nav-links {
      display: none;
      position: absolute;
      top: 100%;
      left: 0;
      width: 100%;
      background: rgba(255, 255, 255, 0.95);
      flex-direction: column;
      padding: 1rem;
      gap: 1rem;
    }

    .nav-links.active {
      display: flex;
    }

    .title-section {
      padding: 0 1rem;
    }

    h2 {
      font-size: 1.2rem;
    }

    .video-container {
      width: 95%;
      margin: 0 auto;
    }
  }

  .button-container {
    margin-top: 2rem;
    display: flex;
    justify-content: center;
  }

  .close-button {
    padding: 0.75rem 2rem;
    background-color: #2c3e50;
    color: white;
    border: 2px solid #2c3e50;
    border-radius: 6px;
    font-size: 1rem;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .close-button:hover {
    background-color: white;
    color: #2c3e50;
  }

  .modal h2 {
    margin: 0 0 1.5rem 0;
  }
</style>
