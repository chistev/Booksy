<script lang="ts">
	import BeBold from "$lib/components/home/BeBold.svelte";
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

<BeBold {currentWord} />

<Modal {showModal} {toggleModal} />