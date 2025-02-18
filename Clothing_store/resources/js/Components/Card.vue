<template>
    <div class="card-container">
        <div class="clothing-card">
            <img :src="product.image" alt="Product Image" class="product-image" />
            <div class="card-info">
                <h3 class="product-name">{{ product.name }}</h3>
                <p class="product-price">${{ product.price }}</p>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        product: {
            type: Object,
            required: true
        }
    }
};
</script>

<style scoped>
.card-container {
    display: flex;
    justify-content: center;
    margin: 15px;
}

.clothing-card {
    width: 100%;
    max-width: 250px;
    margin: 15px;
    background-color: #fff;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.clothing-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 8px 15px rgba(0, 0, 0, 0.3);
}

.product-image {
    width: 100%;
    height: auto;
    object-fit: cover;
    transition: opacity 0.3s ease;
}

.clothing-card:hover .product-image {
    opacity: 0.8;
}

.card-info {
    padding: 10px;
}

.product-name {
    font-size: 1.2em;
    font-weight: bold;
    margin-bottom: 5px;
}

.product-price {
    font-size: 1em;
    color: #333;
}
</style>
