<template>
    <div class="slideshow-container">
        <transition name="slide-fade" mode="out-in">
            <img
                :key="currentImage"
                :src="images[currentImage]"
                class="slide"
                alt="slideshow image"
                v-bind="imageAttributes"
            />
        </transition>

        <!-- Controls (Optional) -->
        <button class="prev" @click="prevImage">&lt;</button>
        <button class="next" @click="nextImage">&gt;</button>
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
                width: '100%',
                height: 'auto',
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
    max-width: 800px;
    margin: auto;
    overflow: hidden;
}

.slide {
    width: 100%;
    height: auto;
    display: block;
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
