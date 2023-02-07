<script lang="ts">
    import type {ActionData} from './$types';
    import { applyAction, enhance } from '$app/forms';
    import { invalidateAll } from '$app/navigation';

    export let form: ActionData;
</script>

<h1 class="ml-4">Login</h1>

<form method="post" action="?/login" use:enhance>
    <div>
        <label for="username">Username</label>
        <input id="username" name="username" type="text" required />
    </div>

    <div>
        <label for="password">Password</label>
        <input id="password" name="password" type="password" required />
    </div>

    {#if form?.invalid}
        <p style:color="red" class="error" >* Username or password are required *</p>       
    {/if}

    {#if form?.credentials}
        <p style:color="red" class="error" >* Username or password is incorrect *</p>       
    {/if}

    <button type="submit">Login</button>
</form>