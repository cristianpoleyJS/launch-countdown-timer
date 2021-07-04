<script>
    const currentDate = new Date()
    const countDownDate = new Date(currentDate.setDate(currentDate.getDate() + 15)).getTime()
    const counter = {
        days: 0,
        hours: 0,
        minutes: 0,
        seconds: 0
    }
    
    setInterval(() => {
    
      const now = new Date().getTime()
    
      const distance = countDownDate - now
    
      counter.days = Math.floor(distance / (1000 * 60 * 60 * 24))
      counter.hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
      counter.minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60))
      counter.seconds = Math.floor((distance % (1000 * 60)) / 1000)
    })
</script>

<main>
    <section>
        {#each Object.keys(counter) as key}
            <div>
                <span class="number">
                    <span class="number-top" />
                    <time>{counter[key]}</time>
                    <span class="number-bottom" />
                </span>
                <span class="title">
                    {key}
                </span>
            </div>
        {/each}
    </section>
</main>
<style scoped>
    section {
        display: grid;
        grid-gap: 2rem;
        grid-template-columns: 25fr 25fr 25fr 25fr;
    }

    span.number {
        font-size: 100px;
        display: block;
        border-radius: 8px;
        padding: 1rem 0;
        color: var(--color-text-timer);
        position: relative;
    }
    span.number:after {
        background-color: var(--color-black);
        content: '';
        border-radius: 8px;
        height: 40px;
        bottom: -10px;
        position: absolute;
        width: 100%;
        left: 0;
        z-index: 0;
    }
    time {
        z-index: 2;
        display: block;
        position: relative;
        overflow: hidden;
    }
    time:before {
        content: '';
        background-color: var(--color-black);
        border-radius: 100%;
        position: absolute;
        left: -8px;
        top: calc(50% - 8px);
        width: 14px;
        height: 14px;
    }
    time:after {
        content: '';
        background-color: var(--color-black);
        border-radius: 100%;
        position: absolute;
        right: -8px;
        top: calc(50% - 8px);
        width: 14px;
        height: 14px;
    }
    span.number-top {
        background-color: #2c2d44;
        width: 100%;
        height: 50%;
        position: absolute;
        top: 0;
        border-radius: 8px;
        left: 0;
        z-index: 1;
    }
    span.number-bottom {
        background-color: #34364f;
        width: 100%;
        height: 50%;
        position: absolute;
        bottom: 0;
        left: 0;
        border-radius: 8px;
        z-index: 1;
    }
    span.title {
        color: var(--bg-color-counter);
        display: block;
        text-transform: uppercase;
        font-size: 16px;
        letter-spacing: 0.4em;
        margin-top: 2rem;
    }
</style>