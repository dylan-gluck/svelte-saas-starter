<section class="container mx-auto px-4 py-8">
	<div class="card mx-auto max-w-md">
		<form class="card-body" method="POST" action="?/login">
			<fieldset class="fieldset">
				<label for="email" class="label">Email</label>
				<input id="email" name="email" type="email" class="input w-full" />

				<label for="password" class="label">Password</label>
				<input id="password" name="password" type="password" class="input w-full" />

				<button class="btn btn-primary mt-3">Login</button>
				<button formaction="?/signup" class="btn btn-neutral mt-3">Sign up</button>
			</fieldset>
		</form>
	</div>
</section>
