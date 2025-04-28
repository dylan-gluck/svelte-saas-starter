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

<header class="container mx-auto flex items-center justify-between gap-3 px-4 py-8">
	<nav class="flex items-center justify-between gap-3">
		<a href="/">Home</a>
		<a href="/">Pricing</a>
	</nav>
	{#if user}
		<button onclick={logout}>Logout</button>
	{:else}
		<a href="/auth">Login</a>
	{/if}
</header>
<main>
	{@render children()}
</main>
