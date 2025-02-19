<template>
    <nav class="navbar">
        <div class="logo">
            <h1><a href="/">ETH3REAL</a></h1>
        </div>
        <ul class="navbar-links">
            <li><a href="/">Home</a></li>
            <li><a href="/about">About</a></li>
            <li><a href="/contact">Contact</a></li>
            <li><a href="/login">Login</a></li>
            <li><a href="/register">Register</a></li>
        </ul>
    </nav>
</template>

<script>
export default {
    name: "NavBar"
};
</script>

<style scoped>
/* Navbar Styling */
.navbar {
    background-color: #000; /* Set background color to black */
    padding: 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.navbar .logo h1 {
    color: #fff; /* Set logo text color to white */
    margin: 0;
}

.navbar .navbar-links {
    list-style: none;
    display: flex;
    margin: 0;
    padding: 0;
}

.navbar .navbar-links li {
    margin-left: 20px;
}

.navbar .navbar-links a {
    color: #fff; /* Set link color to white */
    text-decoration: none;
    font-size: 16px;
    font-weight: 500;
    padding: 10px 15px; /* Added padding for clickable area */
    border-radius: 5px; /* Round the corners */
    transition: background-color 0.3s ease, color 0.3s ease; /* Smooth transition */
}

/* Hover effect for links */
.navbar .navbar-links a:hover {
    background-color: #444; /* Slightly lighter black background */
    color: #fff; /* Keep text color white on hover */
}

/* Media Query for Responsive Design */
@media screen and (max-width: 790px) {
    .navbar .navbar-links {
        display: none; /* Hide navbar links on small screens */
    }
    .navbar .logo h1 {
        font-size: 1.5rem; /* Adjust logo size for smaller screens */
    }
}
</style>
