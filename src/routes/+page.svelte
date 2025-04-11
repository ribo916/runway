<script>
  // You can add any reactive variables or imports here if needed
</script>

<div class="container" style="background-image: url('/resume_bg.png')">
  <div class="title-section">
    <h1>Rich Boesch</h1>
    <h2>Still solving problems. Just in a different color palette.</h2>
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
  .container {
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
    padding-top: 2rem;
  }

  .title-section {
    text-align: center;
    margin-bottom: 2rem;
    color: #2c3e50;
    text-shadow: 2px 2px 4px rgba(255, 255, 255, 0.3);
    padding: 2rem 3rem;
    background: rgba(255, 255, 255, 0.95);
    backdrop-filter: blur(8px);
    border-radius: 12px;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.12), 
                0 4px 8px rgba(0, 0, 0, 0.06);
    transform: translateY(10px);
    border: 1px solid rgba(255, 255, 255, 0.3);
    min-width: 300px;
  }

  h1 {
    font-size: 3rem;
    margin: 0;
    margin-bottom: 0.5rem;
    font-weight: 700;
  }

  h2 {
    font-size: 1.5rem;
    margin: 0;
    font-weight: 400;
    opacity: 0.9;
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
    padding: 0; /* ensure no internal spacing */
    margin: 0 auto; /* center the container */
    display: flex; /* ensure proper sizing of children */
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

  /* Media query for mobile devices */
  @media (max-width: 768px) {
    .title-section {
      padding: 0 1rem;
    }

    h1 {
      font-size: 2rem;
    }

    h2 {
      font-size: 1.2rem;
    }

    .video-container {
      width: 95%;
      margin: 0 auto;
    }
  }
</style>
