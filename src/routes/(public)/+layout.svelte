<script>
	import { goto } from '$app/navigation';

	let { data, children } = $props();
	let { user, supabase } = $derived(data);

	const logout = async () => {
		const { error } = await supabase.auth.signOut();
		if (error) {
			console.error(error);
		}
		goto('/auth');
	};
</script>

<header class="navbar container mx-auto">
	<div class="navbar-start">
		<h1 class="text-xl font-bold">Saas Starter</h1>
	</div>
	<div class="navbar-center">
		<nav class="menu menu-horizontal">
			<li><a href="/">Home</a></li>
			<li><a href="/">Pricing</a></li>
		</nav>
	</div>
	<div class="navbar-end gap-2">
		{#if user}
			<a class="btn btn-primary btn-sm" href="/app/dashboard">Dashboard</a>
			<button class="btn btn-sm" onclick={logout}>Logout</button>
		{:else}
			<a class="btn btn-sm" href="/auth">Login</a>
		{/if}
	</div>
</header>
<main>
	{@render children()}
</main>
