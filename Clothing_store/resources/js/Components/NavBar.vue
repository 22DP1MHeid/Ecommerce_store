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
        <ul :class="{ 'navbar-links': true, 'active': menuActive }">
            <li class="dropdown" @mouseenter="showDropdown = true" @mouseleave="showDropdown = false">
                <a href="#">Women</a>
                <ul v-if="showDropdown" class="dropdown-menu">
                    <li><a href="/women/clothing">Clothing</a></li>
                    <li><a href="/women/shoes">Shoes</a></li>
                    <li><a href="/women/accessories">Accessories</a></li>
                </ul>
            </li>
            <li class="dropdown" @mouseenter="showDropdownMen = true" @mouseleave="showDropdownMen = false">
                <a href="#">Men</a>
                <ul v-if="showDropdownMen" class="dropdown-menu">
                    <li><a href="/men/clothing">Clothing</a></li>
                    <li><a href="/men/shoes">Shoes</a></li>
                    <li><a href="/men/accessories">Accessories</a></li>
                </ul>
            </li>
            <li class="person-icon">
                <a href="/register">
                    <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <circle cx="12" cy="7" r="4"></circle>
                        <path d="M12 14c-4 0-6 1.5-6 4v1h12v-1c0-2.5-2-4-6-4z"></path>
                    </svg>
                </a>
            </li>
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
            showDropdown: false,
            showDropdownMen: false
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
.navbar {
    background-color: #000;
    padding: 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    z-index: 100;
}

.navbar .logo h1 a {
    color: #fff;
    text-decoration: none;
}

.navbar-links {
    list-style: none;
    display: flex;
    margin: 0;
    padding: 0;
    align-items: center;
}

.navbar-links li {
    margin-left: 20px;
    position: relative;
}

.navbar-links a {
    color: #fff;
    text-decoration: none;
    font-size: 16px;
    font-weight: 500;
    padding: 10px 15px;
    border-radius: 5px;
    transition: background-color 0.3s ease;
}

.navbar-links a:hover {
    background-color: #444;
}

.dropdown {
    position: relative;
    display: flex;
    justify-content: center;
}

.dropdown-menu {
    position: absolute;
    top: 100%;
    left: 50%;
    transform: translateX(-50%);
    background-color: #222;
    list-style: none;
    padding: 10px 0;
    margin: 0;
    min-width: max-content;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    text-align: center;
    z-index: 200;
}

.dropdown-menu li {
    padding: 8px 15px;
}

.dropdown-menu a {
    display: block;
    color: #fff;
    text-decoration: none;
}

.dropdown-menu a:hover {
    background-color: #444;
}

.hamburger {
    display: none;
    cursor: pointer;
    flex-direction: column;
    justify-content: space-around;
    height: 30px;
    width: 30px;
}

.hamburger .bar {
    width: 25px;
    height: 4px;
    background-color: #fff;
    border-radius: 5px;
}

.person-icon a,
.cart-icon a {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50px;
    height: 50px;
    background-color: transparent;
    border-radius: 50%;
}

@media screen and (max-width: 790px) {
    .navbar-links {
        display: none;
        flex-direction: column;
        position: absolute;
        top: 60px;
        left: 0;
        background-color: #000;
        width: 100%;
        padding: 20px 0;
        z-index: 150;
    }
    .navbar-links.active {
        display: flex;
    }
    .navbar-links li {
        margin: 10px 0;
    }
    .hamburger {
        display: flex;
    }
}
</style>
