<script>
    import CovidStat from '../components/CovidStat.svelte';
    import CovidChart from '../components/CovidChart.svelte';
    import TableContainer from '../components/TableContainer.svelte';
</script>

<svelte:head>
    <title>Covid 19 US TrackerS</title>
</svelte:head>

<dic class="section header">
    <div class="container">
        <h1>Covid 19 - US</h1>
    </div>
</dic>

<CovidStat />
<CovidChart />
<TableContainer />