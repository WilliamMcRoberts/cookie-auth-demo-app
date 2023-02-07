<script lang="ts">
    import { enhance } from '$app/forms';
	import { page } from '$app/stores';

	// $page.data.user is derived from event.locals.user
</script>

<div class="app">

	<nav>

		{#if !$page.data.user}
			<p>Login or Register</p>
			<a href="/login">Login</a>
			<a href="/register">Register</a>

			{:else}
			<h3>Hello {$page.data.user.name}!</h3>
			<a href="/admin">Admin</a>
	
			<form action="/logout" method="post" use:enhance>
				<button type="submit">Logout</button>
			</form>
		{/if}
		
	</nav>

	<main>
		<slot />
	</main>

</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	a {
		border: 2px solid black;
		text-align: center;
		width: 150px;
		margin: 0 auto;
		background: blue;
		color: #fff;
		font-weight: 700;
		text-decoration: none;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
	}
</style>
