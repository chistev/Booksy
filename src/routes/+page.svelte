<script lang="ts">
    import Header from "$lib/components/home/Header.svelte";
    import Modal from "$lib/components/home/Modal.svelte";

    let showModal = false;
    let currentWord = "Bold"; 
    let words = ["Bold", "Free", "Yourself", "Confident", "Colorful", "Brave"];
    let typingInterval: number;

    function toggleModal() {
        showModal = !showModal;
    }

    function startTyping() {
        let wordIndex = 0;
        let charIndex = 0;
        const typingSpeed = 100; 
        const switchSpeed = 2000;

        function typeWord() {
            if (charIndex < words[wordIndex].length) {
                currentWord = words[wordIndex].slice(0, charIndex + 1);
                charIndex++;
            } else {
                clearInterval(typingInterval);
                setTimeout(() => {
                    wordIndex = (wordIndex + 1) % words.length;
                    charIndex = 0;
                    typingInterval = setInterval(typeWord, typingSpeed);
                }, switchSpeed);
            }
        }

        typingInterval = setInterval(typeWord, typingSpeed);
    }

    import { onMount } from "svelte";
    onMount(() => {
        startTyping();
    });
</script>

<Header {toggleModal} />

<section class="be-bold">
    <div class="content-wrapper">
        <h1>
            <span class="be-text">Be</span>
            <span class="animated-text">{currentWord}</span>
        </h1>
        <p class="subtext">Discover and book beauty & wellness professionals near you</p>

        <div class="search-box">
            <i class="bi bi-search"></i>
            <input type="text" placeholder="Search services or businesses" />
        </div>
    </div>
</section>

<Modal {showModal} {toggleModal} />

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    .be-bold {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background: #000; 
        color: white;
        padding: 2rem 0; 
        text-align: center;
    }

    .content-wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .be-bold h1 {
        font-size: 2.5rem;
        font-weight: bold;
        display: flex; 
        align-items: center; 
    }

    .subtext {
        font-size: 1rem;
        margin-top: 0.5rem; 
        color: #ddd; 
    }

    .be-text {
        margin-right: 0.5rem; 
    }

    .animated-text {
        display: inline-block;
        white-space: nowrap;
        overflow: hidden;
        width: 0;
        animation: typing 1.5s steps(10) forwards, blink 0.75s step-end infinite;
    }

    .search-box {
    display: flex;
    align-items: center;
    background-color: #fff;
    border: 1px solid #ccc;
    border-radius: 50px;
    padding: 0.5rem 1rem;
    width: 100%;
    max-width: 400px; /* Adjust the width as needed */
    margin-top: 1rem;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.search-box i {
    color: #999;
    margin-right: 0.5rem;
}

.search-box input {
    border: none;
    outline: none;
    flex: 1;
    font-size: 1rem;
    color: #333;
}


    @keyframes typing {
        from {
            width: 0;
        }
        to {
            width: max-content;
        }
    }

    @keyframes blink {
        50% {
            border-color: transparent;
        }
    }
</style>
