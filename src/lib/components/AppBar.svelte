<script>

    import { AppBar } from '@skeletonlabs/skeleton';
    import { IconLeaf } from '@tabler/icons-svelte';
</script>

<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
	<svelte:fragment slot="lead">
        <IconLeaf size={48} stroke={1}  />
    </svelte:fragment>
	<h1 class="h1"><span class="gradient-heading">PLANTUX</span></h1>


	<svelte:fragment slot="trail">(actions)</svelte:fragment>
</AppBar>