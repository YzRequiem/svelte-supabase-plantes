<script>

import { ProgressRadial } from '@skeletonlabs/skeleton';

let chartValues = [
   {name: 'Plante 1', value: 75},
    {name: 'Plante 2', value: 50},
    {name: 'Plante 3', value: 25},
]

</script>

<div class="w-full p-24 h-full" >
    <h2 class="h2 ">Mes Plantes</h2>
    <div class="flex flex-col gap-10 w-full h-full  justify-center ">
        <div class="flex gap-5 item-center justify-evenly">
            {#each chartValues as chart}
            <div class="flex flex-col gap-5 justify-center items-center">
                <h4 class="h3 gradient-heading">{chart.name}</h4>
                <ProgressRadial value={chart.value} width={'w-60'} meter={'stroke-primary-500'} track={'stroke-primary-500/30'} stroke={80}>{chart.value}%</ProgressRadial>
            </div>  
            {/each}
        </div>
        
    </div>

</div>