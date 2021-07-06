<script>
    import Countdown from './Countdown.svelte'
  </script>
  
  <section>
    <div>
      <h1>We´re launching soon</h1>
      <Countdown />
    </div>
  </section>
  
  <style scoped>
    section {
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
    @media (max-width: 992px) {
        h1 {
            margin-bottom: 2rem;
            font-size: 22px;
        }

        div {
          top: 40%;
        }
    }
  </style>