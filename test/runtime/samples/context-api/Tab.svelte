<script>
	import { getContext, onDestroy } from 'svelte';
	import { TABS } from './Tabs.svelte';

	const tab = {};
	const { registerTab, unregisterTab, selectTab, selectedTab } = getContext(TABS);

	registerTab(tab);

	onDestroy(() => {
		unregisterTab(tab);
	});
</script>

<button class:selected="{$selectedTab === tab}" on:click="{() => selectTab(tab)}">
	<slot></slot>
</button>