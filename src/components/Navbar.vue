<template>
    <header class="nav">
        <h1>Naomi co</h1>
        <div class="links">
            <RouterLink to="/">Home</RouterLink>
            <button v-if="isAuthenticated" @click="handleLogout" >Logout</button>
            <RouterLink v-if="!isAuthenticated" to="/login" >Login</RouterLink>
            <RouterLink v-if="!isAuthenticated" to="/signup" >Sign up</RouterLink>
        </div>
    </header>
</template>

<script>
    import { computed } from '@vue/reactivity';
    import { useRouter } from 'vue-router';
    import store from '../store';

    export default {
        setup(){
            const router = useRouter()

            const handleLogout = () => {
                store.dispatch('logout').then(() => {
                    router.push('/login')
                })
            }

            const isAuthenticated = computed(() => {
                return store.state.loggedIn
            })

            return {
                isAuthenticated,
                handleLogout
            }
        }
    }
</script>
<style scoped>
    .nav {
        margin-top: 0;
        border-bottom: 1px solid black;
        color: beige;
        display: flex;
        justify-content: space-between;
        align-items: center;
        background: black;
    }
    h1{
        font-size: 3rem;
        margin: 0;
    }
    .links {
        display: flex;
        margin-left: auto;
        justify-content: space-between;
        width: 25%;
        align-items: center;
    }
    .cart {  
        padding: 0.5rem;
    }
    a {
        text-decoration: none;
        border: 2px solid gray;
        font-weight: 500;
        font-size: 1rem;
        padding: 0.5rem 1rem;
        color: gray;
        border-radius: 0.375rem;
        outline: none;
        left: -4px;
        top: -4px;
        z-index: 2;
        transition:0.1s ease-in-out ;
    }
    a:hover {
        color: white;
        background-color: black;
        /*transform: translateY(2px) ;*/
    }

    .router-link-active {
        color: white;
        background-color: black;
        transform: translateY(-2px) ;
        box-shadow:0 0 0 ;
    }

    button {
    border: 2px solid gray;
    border-radius: 0.375rem;
    font-size: 1rem;
    background-color: black;
    color: white;
    padding: 0.5rem 1rem;
    text-align: center;
    cursor: pointer;
}
    @media screen and (max-width: 1024px) {
        .links {
            width: 50%;
        }
    }
    @media screen and (max-width: 400px) {
        .links {
            width: 60%;
        }
         a {
            left: 0;
            top: 0;
            z-index: 2;
             box-shadow: none;
         }
    }
</style>