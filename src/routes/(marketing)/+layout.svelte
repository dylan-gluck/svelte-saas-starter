<script>
	import { Button } from '@/components/ui/button';
	import { goto, invalidate } from '$app/navigation';
	import { onMount } from 'svelte';

	let { data, children } = $props();
	let { session, supabase } = $derived(data);

	onMount(() => {
		const { data } = supabase.auth.onAuthStateChange((_, newSession) => {
			if (newSession?.expires_at !== session?.expires_at) {
				invalidate('supabase:auth');
			}
		});

		return () => data.subscription.unsubscribe();
	});
</script>

<header class="border-b border-border py-6">
	<div class="container flex items-center justify-between gap-4">
		<div class="flex items-center gap-4">
			<a href="/"><h1 class="mr-10 text-2xl font-bold leading-none">abc.</h1></a>
			<a href="/" class="text-sm leading-none">Home</a>
			<a href="/" class="text-sm leading-none">Pricing</a>
		</div>
		<div class="flex items-center gap-4">
			<Button
				size="sm"
				variant="outline"
				onclick={() => {
					goto('/auth/register');
				}}>Create Account</Button
			>
			<Button
				size="sm"
				onclick={() => {
					goto('/auth');
				}}>Login</Button
			>
		</div>
	</div>
</header>
<main>
	{@render children()}
</main>
