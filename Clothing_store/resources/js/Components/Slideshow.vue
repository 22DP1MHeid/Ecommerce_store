<template>
    <div class="slideshow-container">
        <transition name="slide-fade" mode="out-in">
            <div class="slide-container">
                <img
                    :key="currentImage"
                    :src="images[currentImage]"
                    class="slide"
                    alt="slideshow image"
                    v-bind="imageAttributes"
                />
                <div class="overlay">
                    <p>ETH3REAL</p>
                </div>
            </div>
        </transition>
    </div>
</template>

<script>
export default {
    data() {
        return {
            currentImage: 0,
            images: [
                '/Images/Slideshow1.jpg',  // Correct path from the public folder
                '/Images/Slideshow2.jpg',
                '/Images/Slideshow3.jpg',
                '/Images/Slideshow4.webp',
            ],
        };
    },
    computed: {
        imageAttributes() {
            return {
                width: '100%',  // Stretch to fill container width
                height: '800px',  // Fixed height for the images
            };
        },
    },
    methods: {
        nextImage() {
            this.currentImage = (this.currentImage + 1) % this.images.length;
        },
        prevImage() {
            this.currentImage = (this.currentImage - 1 + this.images.length) % this.images.length;
        },
    },
    created() {
        setInterval(() => {
            this.nextImage();
        }, 3000); // Automatically transitions every 3 seconds
    },
};
</script>

<style scoped>
.slideshow-container {
    position: relative;
    width: 100%;
    margin: auto;
    overflow: hidden;
    height: 800px; /* Fixed height for the slideshow container */
}

.slide-container {
    position: relative;
    width: 100%;
    height: 100%;
}

.slide {
    width: 100%;  /* Stretch to full width */
    height: 800px;  /* Fixed height */
    object-fit: cover;  /* Ensures the image fills the container without stretching */
    display: block;
}

.overlay {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: white;
    font-size: 2rem;
    font-weight: bold;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.prev,
.next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    border: none;
    padding: 10px;
    font-size: 18px;
    cursor: pointer;
    z-index: 1;
}

.prev {
    left: 10px;
}

.next {
    right: 10px;
}

/* Transition effects */
.slide-fade-enter-active,
.slide-fade-leave-active {
    transition: opacity 1s ease;
}

.slide-fade-enter,
.slide-fade-leave-to /* .slide-fade-leave-active in <2.1.8 */ {
    opacity: 0;
}
</style>
