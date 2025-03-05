<template>
    <div class="clothing-category-search">
        <!-- Search Bar -->
        <div class="search-bar">
            <input
                v-model="searchQuery"
                @input="searchCategories"
                type="text"
                placeholder="Search for categories..."
                class="form-input"
            />
        </div>

        <!-- Categories List -->
        <div class="categories-list">
            <ul>
                <li v-for="category in filteredCategories" :key="category.id">
                    {{ category.name }}
                </li>
            </ul>

            <!-- No categories found -->
            <div v-if="filteredCategories.length === 0" class="no-categories">
                No categories found.
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        categories: Array, // Pass categories as props from the parent component
    },
    data() {
        return {
            searchQuery: '', // Holds the search input
            filteredCategories: this.categories, // Initially, show all categories
        };
    },
    methods: {
        // Function to filter categories based on search query
        searchCategories() {
            if (this.searchQuery === '') {
                this.filteredCategories = this.categories;
            } else {
                this.filteredCategories = this.categories.filter((category) =>
                    category.name.toLowerCase().includes(this.searchQuery.toLowerCase())
                );
            }
        },
    },
};
</script>

<style scoped>
.clothing-category-search {
    padding: 1rem;
}

.search-bar input {
    width: 100%;
    padding: 0.8rem;
    border: 1px solid #ccc;
    border-radius: 4px;
}

.categories-list {
    margin-top: 1rem;
}

.categories-list ul {
    list-style: none;
    padding: 0;
}

.categories-list li {
    padding: 0.5rem 0;
}

.no-categories {
    margin-top: 1rem;
    color: #888;
}
</style>
