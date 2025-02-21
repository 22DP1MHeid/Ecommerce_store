<template>
    <nav class="navbar">
        <div class="logo">
            <h1><a href="/">ETH3REAL</a></h1>
        </div>
        <div class="hamburger" @click="toggleMenu">
            <span class="bar"></span>
            <span class="bar"></span>
            <span class="bar"></span>
        </div>
        <ul class="navbar-links" :class="{ 'active': menuActive }">
            <li><a href="/">Home</a></li>
            <li><a href="/women">Women</a></li>
            <li><a href="/men">Men</a></li>
            <li><a href="/login">Login</a></li>
            <li><a href="/register">Register</a></li>
        </ul>
    </nav>
</template>

<script>
export default {
    name: "NavBar",
    data() {
        return {
            menuActive: false
        };
    },
    methods: {
        toggleMenu() {
            this.menuActive = !this.menuActive;
        }
    }
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
    position: relative;
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

/* Hamburger menu */
.hamburger {
    display: none;
    cursor: pointer;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    height: 30px;
    width: 30px;
}

.hamburger .bar {
    width: 25px;
    height: 4px;
    background-color: #fff;
    border-radius: 5px;
}

/* Media Query for Responsive Design */
@media screen and (max-width: 790px) {
    .navbar .navbar-links {
        display: none; /* Hide navbar links on small screens */
        width: 100%;
        position: absolute;
        top: 60px;
        left: 0;
        background-color: #000;
        flex-direction: column;
        align-items: center;
        padding: 20px 0;
    }

    .navbar .navbar-links.active {
        display: flex; /* Show links when active */
    }

    .navbar .navbar-links li {
        margin: 10px 0; /* Increase vertical spacing */
    }

    .hamburger {
        display: flex; /* Show hamburger menu on mobile */
    }
}
</style>
