<script>
// @ts-nocheck

    import Homepage from "../pages/Homepage.svelte";
    import { activeRouteDerived, setActiveRoute } from '../activeRoute';
    import { onMount } from 'svelte';

    let activeRoute = '';

    activeRouteDerived.subscribe(value => {
        activeRoute = value;
    });

    onMount(() => {
        setActiveRoute('/');
    });
</script>

<section>
	<div id="searchText">- Search for a song, album or artist</div>
    <Homepage />
</section>

<style>
	section {
        min-height: 100vh;
        background: #050505;
        color:#fff;
        z-index: 0;
		background-image: linear-gradient(to bottom, #1c0949, #050505, #050505, #050505, #050505);
	}
	#searchText {
        opacity: .4;
		font-size: 1rem;
        position: absolute;
        top: 35px;
        left: 770px;
        display: none;
	}
</style>
