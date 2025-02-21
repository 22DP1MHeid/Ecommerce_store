<script setup>
import Navbar from '../Components/NavBar.vue'
import Footer from '../Components/Footer.vue'


</script>

<template>
    <navbar/>
    <div class="container">
        <h1>Privacy Policy</h1>
        <p><strong>Effective Date:</strong> {{ effectiveDate }}</p>
        <p>At {{ storeName }}, your privacy is of the utmost importance to us. This Privacy Policy outlines how we collect, use, and protect your personal information when you visit our website or make purchases from our store.</p>

        <h2>1. Information We Collect</h2>
        <p>We collect both personal and non-personal information in the course of providing our services to you. The types of information we may collect include:</p>

        <h3>Personal Information</h3>
        <p>When you make a purchase, sign up for our newsletter, or create an account, we may collect the following information:</p>
        <ul>
            <li>Name</li>
            <li>Email address</li>
            <li>Shipping and billing address</li>
            <li>Phone number</li>
            <li>Payment information (e.g., credit card details)</li>
        </ul>

        <h3>Non-Personal Information</h3>
        <p>We may automatically collect non-personal information when you visit our website, including:</p>
        <ul>
            <li>IP address</li>
            <li>Browser type and version</li>
            <li>Device information</li>
            <li>Pages you visit on our website</li>
            <li>Time spent on our website</li>
        </ul>

        <h2>2. How We Use Your Information</h2>
        <p>We use your personal information for the following purposes:</p>
        <ul>
            <li>To process your orders and deliver the products you have purchased</li>
            <li>To communicate with you about your order status, promotions, and product updates</li>
            <li>To improve our website and customer service based on your preferences and behavior</li>
            <li>To process payments securely and prevent fraud</li>
            <li>To send marketing communications (with your consent) related to new products, discounts, and promotions</li>
        </ul>

        <h2>3. Sharing Your Information</h2>
        <p>We value your privacy and will never sell or rent your personal information to third parties. However, we may share your information with trusted third-party service providers who assist us in running our store and delivering products (such as payment processors, shipping companies, etc.). These third parties are obligated to keep your information confidential.</p>
        <p>We may also disclose your information if required by law or to protect our rights or the rights of others.</p>

        <h2>4. Cookies and Tracking Technologies</h2>
        <p>We use cookies and similar tracking technologies to enhance your browsing experience, analyze website traffic, and personalize content. Cookies are small text files stored on your device when you visit our website. You can disable cookies in your browser settings, but please note that doing so may impact some features of our website.</p>

        <h2>5. Data Security</h2>
        <p>We implement a variety of security measures to protect your personal information, including encryption and secure payment processing. However, no method of transmission over the internet or electronic storage is 100% secure, so we cannot guarantee absolute security.</p>

        <h2>6. Your Rights</h2>
        <p>You have the right to access, update, or delete your personal information at any time. If you would like to exercise these rights or have any questions regarding your personal data, please contact us at {{ contactEmail }}.</p>
        <p>If you have subscribed to our marketing communications, you may opt-out at any time by clicking the unsubscribe link in our emails or contacting us directly.</p>

        <h2>7. Third-Party Links</h2>
        <p>Our website may contain links to third-party websites. We are not responsible for the privacy practices of these websites. We encourage you to review their privacy policies before providing any personal information.</p>

        <h2>8. Children's Privacy</h2>
        <p>Our website is not intended for use by children under the age of 13. We do not knowingly collect personal information from children. If we become aware that we have inadvertently collected personal information from a child, we will take steps to delete that information as soon as possible.</p>

        <h2>9. Changes to This Privacy Policy</h2>
        <p>We may update this Privacy Policy from time to time. Any changes will be posted on this page, and the "Effective Date" will be updated accordingly. We encourage you to review this Privacy Policy periodically to stay informed about how we are protecting your information.</p>

        <h2>10. Contact Us</h2>
        <p>If you have any questions or concerns about this Privacy Policy or our data practices, please contact us at:</p>
        <p>{{ storeName }}</p>
        <p>{{ storeAddress }}</p>
        <p>{{ contactEmail }}</p>
        <p>{{ contactPhone }}</p>
    </div>
    <footer/>
</template>

<script>
export default {
    props: {
        storeName: {
            type: String,
            default: 'Eth3real'
        },
        effectiveDate: {
            type: String,
            default: 'January 1, 2025'
        },
        storeAddress: {
            type: String,
            default: '123 Main St, City, Country'
        },
        contactEmail: {
            type: String,
            default: 'contact@Eth3real.com'
        },
        contactPhone: {
            type: String,
            default: '+123 456 7890'
        }
    }
};
</script>

<style scoped>
/* Basic Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Body Styling */
body {
    font-family: Arial, sans-serif;
    background-color: #f9f9f9;
    color: #333;
    line-height: 1.6;
    padding: 20px;
    text-align: center;
}

/* Main Container */
.container {
    width: 80%;
    max-width: 900px;
    margin: 0 auto;
    background-color: #fff;
    padding: 30px;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

/* Headings */
h1 {
    font-size: 2.5rem;
    margin-bottom: 20px;
    color: #1a1a1a;
}

h2 {
    font-size: 2rem;
    margin-top: 30px;
    margin-bottom: 15px;
    color: #1a1a1a;
}

h3 {
    font-size: 1.5rem;
    margin-top: 20px;
    margin-bottom: 10px;
    color: #333;
}

/* Paragraphs and Lists */
p {
    font-size: 1rem;
    margin-bottom: 15px;
    color: #555;
}

ul {
    margin-left: 20px;
    list-style-type: disc;
    display: inline-block;
}

ul li {
    margin-bottom: 8px;
}

/* Link Styling */
a {
    color: #007BFF;
    text-decoration: none;
}

a:hover {
    text-decoration: underline;
}
</style>
