<script>
	import { goto } from '$app/navigation';

	let { data, children } = $props();
	let { supabase } = $derived(data);

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
		<a href="/"><h1 class="text-xl font-bold">Saas Starter</h1></a>
	</div>
	<div class="navbar-center">
		<nav class="menu menu-horizontal">
			<li><a href="/app/dashboard" class="menu-active">Dashboard</a></li>
			<li><a href="/app/settings">Settings</a></li>
		</nav>
	</div>
	<div class="navbar-end gap-2">
		<button class="btn btn-sm" onclick={logout}>Logout</button>
	</div>
</header>
<main>
	{@render children()}
</main>
