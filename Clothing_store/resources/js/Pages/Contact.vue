<template>
    <div>
        <!-- Include Navbar Component -->
        <Navbar/>

        <!-- Contact Page Content -->
        <div class="contact-page">
            <div class="container">
                <h1 class="page-title">Contact Us</h1>

                <div class="contact-info">
                    <h2>We'd love to hear from you!</h2>
                    <p>If you have any questions, comments, or just want to say hi, feel free to reach out to us. We are here to assist you.</p>

                    <div class="contact-details">
                        <div class="address">
                            <h3>Our Address</h3>
                            <p>123 Fashion Street, Trendy City, 10001</p>
                        </div>
                        <div class="email">
                            <h3>Email Us</h3>
                            <p>support@yourstore.com</p>
                        </div>
                        <div class="phone">
                            <h3>Call Us</h3>
                            <p>(123) 456-7890</p>
                        </div>
                    </div>
                </div>

                <div class="contact-form">
                    <h2>Send Us a Message</h2>

                    <!-- Contact Form -->
                    <form @submit.prevent="submitForm">
                        <div class="form-group">
                            <label for="name">Your Name</label>
                            <input type="text" id="name" v-model="form.name" required />
                        </div>

                        <div class="form-group">
                            <label for="email">Your Email</label>
                            <input type="email" id="email" v-model="form.email" required />
                        </div>

                        <div class="form-group">
                            <label for="message">Your Message</label>
                            <textarea id="message" v-model="form.message" required></textarea>
                        </div>

                        <button type="submit" class="submit-btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>

        <!-- Include Footer Component -->
        <Footer />
    </div>
</template>

<script>
import NavBar from '@/Components/NavBar.vue';
import Footer from '@/Components/Footer.vue';
import Card from "@/Components/Card.vue";
import Navbar from "@/Components/NavBar.vue";

export default {
    name: 'Contact',
    components: {
        Navbar, Card,
        NavBar,
        Footer
    },
    data() {
        return {
            form: {
                name: '',
                email: '',
                message: ''
            }
        };
    },
    methods: {
        submitForm() {
            // You can handle the form submission here
            console.log('Form Submitted:', this.form);

            // Simulating form submission
            alert('Your message has been sent successfully!');

            // Optionally, you can clear the form after submission
            this.form.name = '';
            this.form.email = '';
            this.form.message = '';
        }
    }
};
</script>

<style scoped>
.contact-page {
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

.contact-info {
    margin-top: 40px;
    text-align: center;
}

.contact-info h2 {
    font-size: 2em;
    color: #333;
    margin-bottom: 20px;
}

.contact-details {
    display: flex;
    justify-content: space-around;
    margin-top: 30px;
}

.contact-details div {
    width: 30%;
    font-size: 1.1em;
}

.contact-details h3 {
    font-size: 1.5em;
    color: #333;
}

.contact-form {
    margin-top: 50px;
    text-align: center;
}

.contact-form h2 {
    font-size: 2em;
    margin-bottom: 30px;
}

.form-group {
    margin-bottom: 20px;
}

.form-group label {
    display: block;
    font-size: 1.1em;
    color: #333;
    margin-bottom: 5px;
}

.form-group input,
.form-group textarea {
    width: 100%;
    padding: 10px;
    font-size: 1em;
    border: 1px solid #ccc;
    border-radius: 5px;
}

.form-group textarea {
    height: 150px;
    resize: none;
}

.submit-btn {
    padding: 10px 20px;
    background-color: #333;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

.submit-btn:hover {
    background-color: #555;
}
</style>
