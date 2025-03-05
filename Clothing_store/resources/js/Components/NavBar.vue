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
        <ul>
            <li><a href="/women">Women</a></li>
            <li><a href="/men">Men</a></li>
            <!-- Person Icon replaced Login and Register -->
            <li class="person-icon">
                <a href="/register">
                    <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <circle cx="12" cy="7" r="4"></circle>
                        <path d="M12 14c-4 0-6 1.5-6 4v1h12v-1c0-2.5-2-4-6-4z"></path>
                    </svg>
                </a>
            </li>
            <!-- Shopping Cart Icon -->
            <li class="cart-icon">
                <a href="/cart">
                    <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M6 6h15l-1.68 10H7.68L6 6z"></path>
                        <circle cx="10" cy="20" r="2"></circle>
                        <circle cx="18" cy="20" r="2"></circle>
                    </svg>
                </a>
            </li>
        </ul>
    </nav>
</template>

<script>
export default {
    name: "NavBar",
    data() {
        return {
            menuActive: false,
            isSearchModalOpen: false,
            searchQuery: ""
        };
    },
    methods: {
        toggleMenu() {
            this.menuActive = !this.menuActive;
        },
        toggleSearchModal() {
            this.isSearchModalOpen = !this.isSearchModalOpen;
        },
        closeSearchModal() {
            this.isSearchModalOpen = false;
        },
        search() {
            // You will later connect this to your Laravel backend
            console.log("Searching for: ", this.searchQuery);
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
    z-index: 100; /* Ensure navbar stays above other content */
}

.navbar .logo h1 {
    color: #fff; /* Set logo text color to white */
    margin: 0;
    font-size: 24px;
}

.navbar .navbar-links {
    list-style: none;
    display: flex;
    margin: 0;
    padding: 0;
    align-items: center; /* Align items in the center */
}

.navbar .navbar-links li {
    margin-left: 20px;
    display: flex;
    align-items: center; /* Ensure items are aligned vertically */
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

/* Person Icon styling */
.navbar .navbar-links .person-icon a {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50px;
    height: 50px;
    background-color: transparent;
    border-radius: 50%;
    transition: background-color 0.3s ease;
}

.navbar .navbar-links .person-icon a svg {
    width: 24px; /* Increased size of the icon */
    height: 24px; /* Increased size of the icon */
}

/* Hover effect for person icon */
.navbar .navbar-links .person-icon a:hover {
    background-color: #444; /* Slightly lighter background on hover */
}

/* Shopping Cart Icon styling */
.navbar .navbar-links .cart-icon a {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50px;
    height: 50px;
    background-color: transparent;
    border-radius: 50%;
    transition: background-color 0.3s ease;
}

.navbar .navbar-links .cart-icon a svg {
    width: 24px; /* Icon size */
    height: 24px;
}

/* Hover effect for cart icon */
.navbar .navbar-links .cart-icon a:hover {
    background-color: #444; /* Slightly lighter background on hover */
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
