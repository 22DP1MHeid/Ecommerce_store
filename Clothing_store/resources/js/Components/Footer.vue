<template>
    <footer class="footer">
        <div class="footer-content">
            <p>&copy; 2025 MyApp. All rights reserved.</p>
            <ul class="footer-links">
                <li><a href="/about">About</a></li>
                <li><a href="/contact">Contact</a></li>
                <li><a href="/privacy">Privacy Policy</a></li>
            </ul>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'Footer'
};
</script>

<style scoped>
/* Footer Styling */
.footer {
    background-color: #222; /* Dark background color */
    color: white;
    padding: 20px 0;
    text-align: center;
    position: relative;
    bottom: 0;
    width: 100%;
}

.footer-content {
    max-width: 1200px;
    margin: 0 auto;
}

.footer p {
    margin: 0;
    font-size: 14px;
}

.footer-links {
    list-style-type: none;
    padding: 0;
    margin: 10px 0 0;
    display: flex;
    justify-content: center;
}

.footer-links li {
    margin: 0 15px;
}

.footer-links a {
    text-decoration: none;
    color: white;
    font-size: 14px;
}

.footer-links a:hover {
    color: #a34faf; /* Hover effect color */
}
</style>
