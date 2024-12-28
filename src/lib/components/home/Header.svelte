<script lang="ts">
    export let toggleModal: () => void;
</script>

<header class="header">
    <div class="logo">booksy</div>

    <nav class="nav">
        <button class="login" on:click={toggleModal}>
            <i class="bi bi-person"></i> Log In / Sign Up
        </button>
    </nav>
</header>

<style>
    .header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem 2rem;
        background: #000;
        color: white;
    }

    .logo {
        font-size: 1.5rem;
        font-weight: bold;
        cursor: pointer;
    }

    .nav {
        display: flex;
        align-items: center;
        gap: 1rem;
    }

    .login {
        background: none;
        border: none;
        color: white;
        font-size: 1rem;
        cursor: pointer;
        display: flex;
        align-items: center;
        gap: 0.5rem;
    }

    .login:hover {
        text-decoration: underline;
    }
</style>
