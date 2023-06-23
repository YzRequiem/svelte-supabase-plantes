<script>
    import { AppRail, AppRailTile, AppRailAnchor } from '@skeletonlabs/skeleton';
    import { page } from '$app/stores';
    import {IconPlant, IconHome2, IconCirclePlus, IconAlertCircle} from '@tabler/icons-svelte'
</script>


<AppRail background=" bg-surface-50-900-token">
	<svelte:fragment slot="lead">
		<AppRailAnchor href="/" >
            <div class="flex items-center justify-center">
                <IconHome2 size={36} stroke={1} />
            </div>
        </AppRailAnchor>
	</svelte:fragment>
	<!-- --- -->
	<AppRailTile name="tile-1" value={0} title="tile-1">
		<svelte:fragment slot="lead">
            <AppRailAnchor href="/plantes" selected={$page.url.pathname === '/plantes'} >
            <div class="flex items-center justify-center">
                <IconPlant  size={36} stroke={1} />
            </div>
            <span>Mes plantes</span>
            </AppRailAnchor>
        </svelte:fragment>
	</AppRailTile>
	<AppRailTile name="tile-2" value={1} title="tile-2">
		<svelte:fragment slot="lead">
            <AppRailAnchor href="/newPlante" selected={$page.url.pathname === '/newPlante'} >
            <div class="flex items-center justify-center">
                <IconCirclePlus  size={36} stroke={1} />
            </div>
            <span>Ajouter une plante</span>
            </AppRailAnchor>
        </svelte:fragment>
	</AppRailTile>
	<AppRailTile name="tile-3" value={2} title="tile-3">
		<svelte:fragment slot="lead">
            <AppRailAnchor href="/alerts" selected={$page.url.pathname === '/alerts'} >
            <div class="flex items-center justify-center">
                <IconAlertCircle  size={36} stroke={1} />
            </div>
            <span>Alertes</span>
            </AppRailAnchor>
        </svelte:fragment>
	</AppRailTile>
	<!-- --- -->
	<svelte:fragment slot="trail">
        <div class="flex items-center justify-center">

            <AppRailAnchor href="/" target="_blank" title="Account">(icon)</AppRailAnchor>
        </div>
	</svelte:fragment>
</AppRail>
