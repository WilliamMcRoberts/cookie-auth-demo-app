<script lang="ts">
    import {page} from '$app/stores';
</script>

<h1>Admin Page</h1>

{#if $page.data.user.role === 'ADMIN'}

    <p>Welcome Admin {$page.data.user.name}</p>

    <form action='/logout' method="post">
        <button type="submit">Logout</button>
    </form>

    {:else}
    <p style="color: orangered;">* You are not an admin. *</p>
    
{/if}