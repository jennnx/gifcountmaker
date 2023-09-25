<script>
    import FollowerIcon from "./followers.svelte";
    import { tweened } from "svelte/motion";
    import { quintOut } from "svelte/easing";
    import { onMount } from "svelte";
    import { Confetti } from "svelte-confetti";

    let count = tweened(0, {
        duration: 2000,
        easing: quintOut,
    });
    let subtitle = "Amazing followers";

    $: trunc = Math.trunc($count);

    let show = false;

    onMount(() => {
        setTimeout(() => {
            count.set(1000);
        }, 1000);
        setTimeout(() => {
            show = true;
        }, 3200);
    });
</script>

<div class="container">
    <div class="content">
        <div class="confetti">
            {#if show}
                <Confetti size={10} amount={150} x={[-2, 2]} />
            {/if}
        </div>
        <div class="icon-container">
            <FollowerIcon />
        </div>
        <div class="text-container">
            <p class="count">{trunc}</p>
            <p class="subtitle">{subtitle}</p>
        </div>
    </div>
</div>

<style lang="scss">
    .container {
        font-family: "Inter", sans-serif;
        margin: 400px auto;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 320px;
        height: 140px;
        padding: 20px 50px;
        /* Replace with your own gradient */
        background: linear-gradient(
            90deg,
            rgba(2, 0, 36, 1) 0%,
            rgba(93, 219, 255, 0.9) 0%,
            rgba(194, 86, 255, 0.8) 100%
        );
    }

    .content {
        width: 320px;
        padding: 20px 20px;
        display: flex;
        flex-direction: row;
        justify-content: flex-start;
        align-items: center;
        background: white;
        border-radius: 16px;
    }

    .icon-container {
        height: 45px;
        width: 45px;
        color: rgb(60 130 250);
        background-color: rgb(200 230 250);
        border-radius: 9999px;
        font-size: 1.75rem;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .text-container {
        display: flex;
        flex-direction: column;
        margin-left: 1.25rem;
        padding: 0;
    }

    .count {
        margin: 0;
        color: black;
        font-weight: 700;
        font-size: 1.5rem;
    }

    .subtitle {
        margin: 0;
        color: black;
        font-weight: 300;
        font-size: 0.8rem;
    }

    .confetti {
        position: absolute;
        margin-left: 120px;
        margin-top: 150px;
    }
</style>
