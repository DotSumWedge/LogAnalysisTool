<script>
	import FileInput from "./components/FileInput.svelte";
	import ClassicAnalysis from "./components/ClassicAnalysis.svelte";
	import TimeSeriesPlot from "./components/TimeSeriesPlot.svelte";
	import IsolationForestResults from "./components/IsolationForestResults.svelte";
	import PULLAnomalyResults from "./components/PULLAnomalyResults.svelte";
	import ClusterAnomalyResults from "./components/ClusterAnomalyResults.svelte";
	import UserPrompt from "./components/UserPrompt.svelte";
	import AnalysisSummary from "./components/AnalysisSummary.svelte";
  
	let showAnalysisSummary = false;

	function handleUserPromptSubmit(event) {
		showAnalysisSummary = true;
	}
</script>

<h1>Log Analysis</h1>
<FileInput />
<ClassicAnalysis />
<TimeSeriesPlot title="Data Size Over Time Plot Goes Here" />
<TimeSeriesPlot title="Messages Per Second Over Time Plot Goes Here" />
<IsolationForestResults />
<PULLAnomalyResults />
<ClusterAnomalyResults />
<UserPrompt on:submit={handleUserPromptSubmit} />

{#if showAnalysisSummary}
	<AnalysisSummary />
{/if}

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Log Analysis Tool" />
</svelte:head>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
