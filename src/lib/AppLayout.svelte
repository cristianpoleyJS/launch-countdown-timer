<script>
    import Countdown from './Countdown.svelte'
  </script>
  
  <main>
    <div>
      <p>We´re launching soon</p>
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
  
    p {
      color: var(--color-text-white);
      text-transform: uppercase;
      letter-spacing: 0.3em;
      margin-bottom: 7rem;
      font-size: 28px;
    }

    div {
      margin: 0 auto;
      position: absolute;
      left: 50%;
      top: 35%;
      transform: translate(-50%, -50%);
      text-align: center;
      width: 100%;
      max-width: 836px;
      padding: 0 2rem;
    }
  </style>