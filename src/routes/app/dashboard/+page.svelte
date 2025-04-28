<script>
	let { data } = $props();
	let { user } = $derived(data);
</script>

<div class="container mx-auto px-4 py-8">
	<h1 class="text-3xl font-bold">Dashboard</h1>
	<p>Logged in user {user?.email ?? 'Unknown'}</p>
</div>
