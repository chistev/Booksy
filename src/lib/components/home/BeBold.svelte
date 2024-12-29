<script lang="ts">
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

<section class="appointments-better">
    <div class="appointments-wrapper">
        <div class="text-section">
            <h2>Appointments done better</h2>
            <p>
                Looking for your next appointment with a local barber, hair stylist, massage therapist or nail artist? Need appointment booking for a beard trim, an eyebrow wax, or a deep tissue massage?
            </p>
            <p>
                Booksy is a free beauty scheduling app and makes appointments easy to find and book within seconds. No more phone tag. Book anytime, from anywhere, 24/7.
            </p>
            <strong>Discover top businesses in your area and book instantly with Booksy.</strong>
        </div>
        <div class="illustration-section">
            <svg xmlns="http://www.w3.org/2000/svg" width="300" height="200" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <rect x="2" y="6" width="20" height="14" rx="2" ry="2" fill="#e3f2fd"></rect>
                <path d="M2 10h20"></path>
                <circle cx="12" cy="16" r="2" fill="#2196f3"></circle>
                <path d="M5 6l1-2m12 2l-1-2"></path>
                <rect x="8" y="2" width="8" height="2" rx="1" ry="1" fill="#bbdefb"></rect>
                <circle cx="18" cy="18" r="3" stroke="#2196f3" fill="none"></circle>
                <path d="M21 21l-1.5-1.5"></path>
            </svg>
        </div>
    </div>
</section>

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

    .appointments-better {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 2rem;
        background-color: #f9f9f9;
        color: #333;
    }

    .appointments-wrapper {
        display: flex;
        max-width: 1000px;
        gap: 2rem;
        align-items: center;
        flex-wrap: wrap;
    }

    .text-section {
        flex: 1;
        font-size: 1rem;
    }

    .text-section h2 {
        font-size: 2rem;
        margin-bottom: 1rem;
    }

    .illustration-section {
        flex: 1;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .illustration-section svg {
        width: 100%;
        max-width: 300px;
        height: auto;
    }
</style>
