<script>
    let isDarkMode = false;

    function ToggleMode() {
        document.body.classList.toggle("dark-mode");
        isDarkMode = !isDarkMode;
    }
</script>

<nav class:is-dark-mode={isDarkMode}>
    <button on:click={ToggleMode} class:is-dark-mode={isDarkMode}>
        {isDarkMode ? "Light Mode" : "Dark Mode"}
    </button>
</nav>

<style>
    :global(nav) {
        padding: 10px;
        background-color: #f0f0f0;
    }

    :global(nav.is-dark-mode) {
        background-color: black;
        color: white;
    }
    /* Light mode (default) */
    :global(.container) {
        background-color: white;
        color: black;
        font-size: 25px;
        transition:
            background-color 0.3s,
            color 0.3s;
    }

    /* Dark mode */
    :global(.container.dark-mode) {
        background-color: black;
        color: white;
    }

    button {
        padding: 10px 15px;
        font-size: 16px;
        cursor: pointer;
        background-color: black;
        border: none;
        color: white;
        border-radius: 5px;
        transition:
            background-color 0.3s,
            color 0.3s;
    }

    /* Hover effect for button */
    button:hover {
        background-color: red;
    }

    /* Dark mode button styles */
    button.is-dark-mode {
        background-color: white;
        color: black;
    }
    button.is-dark-mode:hover {
        background-color: red;
    }
</style>
