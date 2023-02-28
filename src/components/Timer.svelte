<script lang="ts">

let timeMin = 25
let timeSec = 0

var timer = () => setInterval(() => {
	if (timeSec === 0) {
		timeSec = 59
		timeMin -= 1
	} else {
		timeSec -= 1
	}
	if (timeMin === 0 && timeSec === 0) {
		clearInterval(timer())
	}
}, 1000)

const handleStartTimer = () => {
	timer()
}

const handleStopTimer = () => {
	// TODO: THE TIMER MUST BE STOPPED BATMAN!
	// clearInterval(timer())
}

</script>

<div class="timer">
	<h1 class="title">Pomo Timer</h1>
	<div class='time'>{`${timeMin}:${timeSec < 10 ? '0' + timeSec : timeSec}`}</div>
	<div class='buttons'>
		<button on:click={handleStartTimer}>Start</button>
		<button on:click={handleStopTimer}>Stop</button>
	</div>
</div>

<style>

	.title {
		text-align: center;
	}

	.time {
		font-size: 5em;
		text-align: center;
		margin-bottom: 40px;
	}

	.buttons {
		display: flex;
		justify-content: space-between;
		width: 20em;
	}

	button {
		width: 8em;
		height: 2em;
		background-color: var(--color-theme-1);
		border: 1px solid var(--color-theme-1);
		border-radius: .2em;
	}

	button:hover {
		background-color: var(--color-theme-2);
		border: 1px solid var(--color-theme-2);
		cursor: pointer;
	}

</style>
