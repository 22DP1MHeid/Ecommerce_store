<template>
    <div class="product-container">
        <!-- Loop over the products array and display each product as a card -->
        <div class="product-card" v-for="(product, index) in products" :key="index">
            <div class="product-image">
                <!-- Placeholder for product image -->
                <img :src="product.image || '/path/to/placeholder.jpg'" alt="product image" />
            </div>
            <div class="product-info">
                <h3>{{ product.name }}</h3>
                <p class="price">${{ product.price.toFixed(2) }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            // Placeholder products for demonstration
            products: [
                { image: '../Images/Product1.png', name: 'Product 1', price: 19.99 },
                { image: '../Images/Product2.png', name: 'Product 2', price: 29.99 },
                { image: '../Images/Product3.png', name: 'Product 3', price: 39.99 },
                { image: '../Images/Product4.png', name: 'Product 4', price: 49.99 },
                { image: '../Images/Product5.png', name: 'Product 5', price: 59.99 },
                { image: '../Images/Product6.png', name: 'Product 6', price: 69.99 },
                { image: '../Images/Product7.png', name: 'Product 7', price: 79.99 },
                { image: '../Images/Product8.png', name: 'Product 8', price: 89.99 },
            ],
        };
    },
};
</script>

<style scoped>
/* Container for the entire product list */
.product-container {
    display: flex;
    flex-wrap: wrap; /* Allows items to wrap when needed */
    justify-content: space-between; /* Distribute products evenly */
    gap: 20px; /* Space between cards */
    padding: 20px;
}

/* Individual product card style */
.product-card {
    width: 23%; /* 4 products per row when full width */
    box-sizing: border-box;
    background-color: #fff;
    border: 1px solid #ddd;
    border-radius: 8px;
    overflow: hidden;
    transition: transform 0.3s ease-in-out;
}

.product-card:hover {
    transform: translateY(-5px); /* Hover effect for the product cards */
}

/* Style for the image section */
.product-image {
    width: 100%;
    height: 500px; /* Fixed height for the image */
    overflow: hidden;
    position: relative;
}

.product-image img {
    width: 100%;
    height: 100%;
    object-fit: cover; /* Ensures images fill the container without distortion */
}

/* Product information section */
.product-info {
    padding: 15px;
    text-align: center;
}

/* Price styling */
.price {
    font-size: 1.2rem;
    color: #333;
    font-weight: bold;
}

/* Responsive design for smaller screens */
@media (max-width: 1200px) {
    .product-card {
        width: 48%; /* 2 products per row */
    }
}

@media (max-width: 768px) {
    .product-card {
        width: 100%; /* 1 product per row */
    }
}
</style>
