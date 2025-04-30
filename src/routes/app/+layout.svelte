<script>
	import { goto } from '$app/navigation';
	import { Button } from '@/components/ui/button';

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

<header class="border-b border-border py-6">
	<div class="container flex items-center justify-between gap-4">
		<div class="flex items-center gap-4">
			<a href="/"><h1 class="mr-10 text-2xl font-bold leading-none">abc.</h1></a>
			<a href="/app/dashboard" class="text-sm leading-none">Dashboard</a>
			<a href="/app/settings" class="text-sm leading-none">Settings</a>
		</div>
		<div class="flex items-center gap-4">
			<Button size="sm" variant="outline" onclick={logout}>Logout</Button>
		</div>
	</div>
</header>
<main>
	{@render children()}
</main>
