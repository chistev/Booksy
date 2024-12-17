<script>
    let showModal = false; 

    function toggleModal() {
        showModal = !showModal;
    }
</script>

<header class="header">
    <div class="logo">booksy</div>

    <nav class="nav">
        <button class="login" on:click={toggleModal}>
            <i class="bi bi-person"></i> Log In / Sign Up
        </button>
        <button class="cta-button">List your business</button>
    </nav>
</header>

{#if showModal}
    <div class="modal-backdrop" on:click={toggleModal}>
        <div class="modal" on:click|stopPropagation>
            <button class="close" on:click={toggleModal}>&times;</button>
            <h2>Get started</h2>
            <p>Create an account or log in to book and manage your appointments.</p>
            <input type="email" placeholder="Email" class="input-field" />
            <button class="continue-button">Continue</button>
            <div class="divider">OR</div>
            <button class="social-button facebook">
                <i class="bi bi-facebook"></i> Continue with Facebook
            </button>
            <button class="social-button apple">
                <i class="bi bi-apple"></i> Continue with Apple
            </button>
            <button class="social-button google">
                <img src="https://www.google.com/favicon.ico" alt="Google" class="google-icon" />
                Continue with Google
            </button>
        </div>
    </div>
{/if}

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

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

    .cta-button {
        background: white;
        color: black;
        border: none;
        padding: 0.5rem 1rem;
        border-radius: 0.5rem;
        font-weight: bold;
        cursor: pointer;
    }

    .cta-button:hover {
        background: #ddd;
    }

    .modal-backdrop {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.5);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 999;
    }

    .modal {
        background: white;
        width: 400px;
        padding: 2rem;
        border-radius: 8px;
        position: relative;
        text-align: center;
    }

    .modal h2 {
        font-size: 1.5rem;
        margin-bottom: 0.5rem;
    }

    .modal p {
        font-size: 0.9rem;
        margin-bottom: 1rem;
    }

    .close {
        position: absolute;
        top: 0.5rem;
        right: 0.5rem;
        background: none;
        border: none;
        font-size: 1.5rem;
        cursor: pointer;
    }

    .input-field {
        width: 100%;
        padding: 0.5rem;
        margin-bottom: 1rem;
        border: 1px solid #ccc;
        border-radius: 4px;
    }

    .continue-button {
        width: 100%;
        background: #e6e6e6;
        color: #888;
        border: none;
        padding: 0.75rem;
        font-weight: bold;
        margin-bottom: 1rem;
        border-radius: 4px;
        cursor: not-allowed;
    }

    .divider {
        margin: 1rem 0;
        font-size: 0.8rem;
        color: #aaa;
        position: relative;
    }

    .divider::before,
    .divider::after {
        content: "";
        position: absolute;
        top: 50%;
        width: 40%;
        height: 1px;
        background: #ccc;
    }

    .divider::before {
        left: 0;
    }

    .divider::after {
        right: 0;
    }

    .social-button {
        width: 100%;
        padding: 0.75rem;
        margin-bottom: 0.5rem;
        border: none;
        border-radius: 4px;
        font-weight: bold;
        cursor: pointer;
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 0.5rem;
    }

    .social-button.facebook {
        background: #1877f2;
        color: white;
    }

    .social-button.apple {
        background: #000;
        color: white;
    }

    .social-button.google {
        background: #fff;
        border: 1px solid #ccc;
        color: black;
    }

    .google-icon {
        width: 16px;
        height: 16px;
    }
</style>
