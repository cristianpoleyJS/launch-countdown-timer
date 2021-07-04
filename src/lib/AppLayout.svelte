<script>
    import Countdown from './Countdown.svelte'
  </script>
  
  <main>
    <div>
      <h1>We´re launching soon</h1>
      <Countdown />
    </div>
  </main>
  
  <style scoped>
    main {
      background-image: url('../assets/images/bg-stars.svg');
      background-position: center;
      background-size: auto;
      height: 100vh;
    }
  
    h1 {
      color: var(--color-text-white);
      text-transform: uppercase;
      letter-spacing: 0.3em;
      margin-bottom: 7rem;
    }

    div {
      margin: 0 auto;
      position: absolute;
      left: 50%;
      top: 35%;
      transform: translate(-50%, -50%);
      text-align: center;
      width: 100%;
      max-width: 800px;
    }
  </style>