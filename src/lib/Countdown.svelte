<script>
    let finish = false

    const formatDate = (date) => {
        return date < 10 ? `0${date}` : date
    }

    const calculateDays = (difference) => {
        return formatDate(Math.floor((difference) / (1000 * 60 * 60 * 24)))
    }

    const calculateHours = (difference) => {
        return formatDate(Math.floor(((difference) % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)))
    }

    const calculateMinutes = (difference) => {
        return formatDate(Math.floor(((difference) % (1000 * 60 * 60)) / (1000 * 60)))
    }

    const calculateSeconds = (difference) => {
        return formatDate(Math.floor(((difference) % (1000 * 60)) / 1000))
    }

    const currentDate = new Date()
    const countdownDate = new Date(currentDate.getFullYear(), currentDate.getMonth(), currentDate.getDate() + 15, 0, 0, 0).getTime()
    const counter = {
        days: calculateDays(countdownDate - currentDate.getTime()),
        hours: calculateHours(countdownDate - currentDate.getTime()),
        minutes: calculateMinutes(countdownDate - currentDate.getTime()),
        seconds: calculateSeconds(countdownDate - currentDate.getTime())
    }
    
    const interval = setInterval(() => {

        const today = new Date().getTime()

        const distance = countdownDate - today

        counter.days = calculateDays(distance)
        counter.hours = calculateHours(distance)
        counter.minutes = calculateMinutes(distance)
        counter.seconds = calculateSeconds(distance)

        if (distance <= 0) {
            clearInterval(interval)
            finish = true
        }
    }, 1000)
</script>

<div>
    {#if !finish}
        <section>
            {#each Object.keys(counter) as key}
                <div>
                    <span class="number">
                        <span class="number-top" />
                        <span class="number-date">{counter[key]}</span>
                        <span class="number-bottom" />
                    </span>
                    <span class="title">
                        {key}
                    </span>
                </div>
            {/each}
        </section>
    {:else}
        <p class="finish">
           Let's go!
        </p>
    {/if}
</div>
<style scoped>
    section {
        display: grid;
        grid-gap: 2rem;
        grid-template-columns: var(--grid-template-columns-counter);
    }

    span.title {
        color: var(--color-counter-title);
        display: block;
        text-transform: uppercase;
        font-size: var(--font-size-counter-title);
        letter-spacing: 0.4em;
        margin-top: 2rem;
    }
    span.number,
    p.finish  {
        font-size: var(--font-size-counter-number);
        display: block;
        border-radius: 8px;
        padding: 1rem 0;
        color: var(--color-counter-number);
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
    }
    span.number-top,
    span.number-bottom {
        width: 100%;
        height: 50%;
        position: absolute;
        border-radius: 8px;
        z-index: 1;
    }
    span.number-top {
        background-color: var(--bg-color-top-counter);
        top: 0;
        left: 0;
    }
    span.number-bottom {
        background-color: var(--bg-color-bottom-counter);
        bottom: 0;
        left: 0;
    }
    span.number-date {
        z-index: 2;
        display: block;
        position: relative;
        overflow: hidden;
    }
    span.number-date:before,
    span.number-date::after {
        content: '';
        background-color: var(--color-black);
        border-radius: 100%;
        position: absolute;
        width: 14px;
        height: 14px;
        top: calc(50% - 7px);
    }
    span.number-date:before {
        left: -8px;
    }
    span.number-date:after {
        right: -8px;
    }
</style>