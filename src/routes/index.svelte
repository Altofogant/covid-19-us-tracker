<script context="module">
    import requests from '../data/requests.js';

    export async function preload() {
        try {
            const usStats = await requests.usStats();
            const historic = await requests.historicUS();
            const statesData = await requests.statesData();
            return {usStats, historic, statesData};
        } catch(e) {
            this.error(500, "There was an error in calling the api, please try again in 5 minutes.");
        }
    }
</script>

<script>
    import CovidStat from '../components/CovidStat.svelte';
    import CovidChart from '../components/CovidChart.svelte';
    import TableContainer from '../components/TableContainer.svelte';

    export let usStats;
    export let historic;
    export let statesData;
</script>

<svelte:head>
    <title>Covid 19 US TrackerS</title>
</svelte:head>

<dic class="section header">
    <div class="container">
        <h1>Covid 19 - US</h1>
    </div>
</dic>

<CovidStat {...usStats}/>
<CovidChart historicData={historic} title="US Covid-19"/>
<TableContainer data={statesData}/>