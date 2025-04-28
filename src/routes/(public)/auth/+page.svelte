<div class="container mx-auto px-4 py-8">
	<form class="mx-auto flex max-w-lg flex-col rounded-lg border p-6" method="POST" action="?/login">
		<label>
			Email
			<input name="email" type="email" />
		</label>
		<label>
			Password
			<input name="password" type="password" />
		</label>
		<button>Login</button>
		<button formaction="?/signup">Sign up</button>
	</form>
</div>
