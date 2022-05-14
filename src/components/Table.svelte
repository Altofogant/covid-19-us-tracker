<script>
    import format from '../data/format.js';
    export let states;

    function formatNum(number) {
        return format.number(number);
    }
</script>

<style>
    table {
        width: 100%;
    }

    .section {
        padding: 0.5rem 1.5rem;
    }
</style>

<div class="section">
    <div class="container">
        <table class="table is-bordered is-striped">
            <thead>
                <tr>
                    <th>State</th>
                    <th>Cases</th>
                    <th>Deaths</th>
                    <th>Total Tested</th>
                </tr>
            </thead>
            <tbody>
                {#each states as state (state.state)}
                    <tr>
                        <td>
                            <a rel="prefetch" href="{state.state}">
                                {state.fullStateName}
                            </a>
                        </td>
                        <td>
                            {formatNum(state.cases)}
                        </td>
                        <td>
                            {formatNum(state.deaths)}
                        </td>
                        <td>
                            {formatNum(state.tested)}
                        </td>
                    </tr>
                {/each}
            </tbody>
        </table>
    </div>
</div>