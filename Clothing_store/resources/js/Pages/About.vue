<template>
    <div>
        <!-- Include Navbar Component -->
        <Navbar />

        <!-- About Page Content -->
        <div class="about-page">
            <div class="container">
                <h1 class="page-title">About Us</h1>
                <div class="content">
                    <section class="brand-story">
                        <h2>Our Story</h2>
                        <p>
                            Welcome to [Your Store Name], a place where fashion meets comfort!
                            We started with the goal of providing high-quality, stylish clothing
                            that everyone can afford. Our collection is carefully curated to ensure
                            the latest trends while prioritizing comfort and sustainability.
                        </p>
                    </section>

                    <section class="mission">
                        <h2>Our Mission</h2>
                        <p>
                            At [Your Store Name], our mission is to bring you the best in fashion
                            without compromise. We aim to provide a shopping experience that is
                            not only easy but also enjoyable, with products that speak to your
                            unique style.
                        </p>
                    </section>

                    <section class="values">
                        <h2>Our Values</h2>
                        <ul>
                            <li>Quality: We focus on providing durable and long-lasting clothing.</li>
                            <li>Sustainability: We are committed to reducing our environmental impact.</li>
                            <li>Customer Satisfaction: We strive for the best service and satisfaction.</li>
                            <li>Innovation: We keep up with fashion trends to keep our collections fresh.</li>
                        </ul>
                    </section>
                </div>

                <div class="team">
                    <h2>Meet the Team</h2>
                    <div class="team-members">
                        <div class="team-member">
                            <img src="team-member-1.jpg" alt="Team Member" />
                            <p>John Doe - Founder</p>
                        </div>
                        <div class="team-member">
                            <img src="team-member-2.jpg" alt="Team Member" />
                            <p>Jane Smith - Lead Designer</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Include Footer Component -->
        <Footer />
    </div>
</template>

<script>
import Navbar from '@/Components/NavBar.vue';
import Footer from '@/Components/Footer.vue';

export default {
    name: 'About',
    components: {
        Navbar,
        Footer
    }
};
</script>

<style scoped>
.about-page {
    font-family: Arial, sans-serif;
    padding: 20px;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
}

.page-title {
    font-size: 2.5em;
    font-weight: bold;
    text-align: center;
    margin-bottom: 20px;
}

.content {
    margin-top: 40px;
}

section {
    margin-bottom: 30px;
}

h2 {
    font-size: 1.8em;
    color: #333;
    margin-bottom: 15px;
}

p {
    font-size: 1.2em;
    line-height: 1.5;
    color: #555;
}

ul {
    list-style-type: none;
    padding: 0;
}

ul li {
    font-size: 1.2em;
    margin-bottom: 10px;
}

.team {
    margin-top: 50px;
    text-align: center;
}

.team-members {
    display: flex;
    justify-content: center;
    gap: 20px;
}

.team-member {
    text-align: center;
}

.team-member img {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    object-fit: cover;
    margin-bottom: 10px;
}

.team-member p {
    font-size: 1.1em;
    color: #333;
}
</style>
