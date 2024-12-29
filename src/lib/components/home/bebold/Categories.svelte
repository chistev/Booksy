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

<style>
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
</style>
