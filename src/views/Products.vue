<template>
    <h1>Products</h1>
    <div class="container">
        <div v-if="loading" class="loader">
            <Loader />
        </div>
        <div 
            v-else 
            v-for="product in products"
            :key="product.id"
            class="products"
            @click="$event => $router.push(`/products/${product.id}`)"
            >
            <div class="images"><img :src="product.thumbnail || product.images[0]" alt=""></div>
            <h2>{{ product.title }}</h2>
            <button @click="$event => $router.push(`/products/${product.id}`)">Buy Now</button>
        </div>
    </div>
</template>

<script>
    import {ref} from '@vue/reactivity'
    import { onMounted } from 'vue';
    import Loader from '../components/Loader.vue'

    export default {
        components: {Loader},
        setup(){
            const products = ref([])
            const loading = ref(true)

            const fetchProducts = () => {
                const endpoint = 'https://dummyjson.com/products?limit=20'
                fetch(endpoint)
                    .then((response) => response.json())
                    .then((response) => (products.value = response.products))
                    .finally(() => (loading.value = false))
            }
            onMounted(() => {
                fetchProducts()
            })
            return {
                products,
                loading
            }
        }
    }
</script>

<style scoped>
.container {
    position: relative;
    color: white;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 3rem 1rem;
    margin: 2rem 1rem;
    min-height: 50vh;
}
h1 {
    font-weight: 200;
    color: bisque;
    margin: 1rem;
    text-align: center;
}
h2 {
    text-align: center;
    margin-top: 2rem;
    font-weight: 200;
    font-size: 1rem;
}
.products {
    display: flex;
    height: 20rem;
    flex-direction: column;
    border: 2px solid white;
    border-radius: 0.5rem;
    cursor: pointer;
}
.images{
    height: 10rem;
}
img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    margin: 0;
    border-top-left-radius: 0.5rem;
    border-top-right-radius: 0.5rem;
}
.loader {
    position: absolute;
    display: flex;
    z-index: 0;
    top: 0px;
    right: 0px;
    bottom: 0px;
    left: 0px;
    justify-content: center;
    align-items: center;
}
button {
    margin: 0 auto;
    margin-top: 1.5rem;
    border: 2px solid white;
    border-radius: 0.375rem;
    font-size: 1rem;
    background-color: blue;
    color: white;
    width: 90%;
    padding: 0.5rem 1.25rem;
    text-align: center;
    cursor: pointer;
    outline: none;
    left: -2px;
    top: -2px;
    z-index: 2;
    transition:0.1s ease-in-out ;
}

button:hover {
    background-color: black;
    color: white;
    transform: translateY(2px) ;
}
</style>