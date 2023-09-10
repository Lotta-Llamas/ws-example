<script lang="ts">

	import { onMount } from 'svelte';

	let connected = false;
	let ws: any;
	export let messages = [];

	onMount(() => {
		ws = new WebSocket('ws://localhost:8080');

		ws.addEventListener('open', () => {
			connected = true;
		})

		ws.addEventListener("message", (event) => {
			messages.push(event.data)
			messages = messages;
		})
	})

	const sendWS = () => {
		ws.send('bid!')
	}

</script>

Web Socket Demo

{#each messages as message}
	{message}
{/each}

<button on:click={sendWS}>Place Bid</button>
