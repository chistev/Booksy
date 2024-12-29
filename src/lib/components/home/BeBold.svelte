<script lang="ts">
	import AppointmentsBetter from "./bebold/AppointmentsBetter.svelte";

    export let currentWord: string;
</script>

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

        <div class="categories mt-5">
            <span>Hair Salon</span>
            <span>Barbershop</span>
            <span>Nail Salon</span>
            <span>Skin Care</span>
            <span>Brows & Lashes</span>
            <span>Massage</span>
            <span>Makeup</span>
            <span>Wellness & Day Spa</span>
            <span class="more">More...</span>
        </div>
    </div>
</section>

<AppointmentsBetter />

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
        max-width: 400px;
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

    .categories {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 1rem;
        margin-top: 1rem;
        font-size: 0.9rem;
    }

    .categories span {
        cursor: pointer;
        padding: 0.5rem 1rem;
        border-radius: 20px;
        background-color: rgba(255, 255, 255, 0.1);
        transition: background-color 0.3s ease, color 0.3s ease;
    }

    .categories span:hover {
        background-color: #fff;
        color: #000;
    }

    .categories .more {
        font-weight: bold;
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
