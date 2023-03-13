<template>
    <div class="container">
        <h1>The page you're looking for can't be found.</h1>
        <RouterLink to="/">Okay</RouterLink>
    </div>
</template>

<style scoped>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        min-height: 75vh;
    }
    h1 {
        font-weight: 200;
        color: white;
        text-align: center;
    }
    a {
  text-decoration: none;
  border: 2px solid white;
  font-size: 1rem;
  font-weight: 500;
  padding: 0.5rem 1rem;
  color: white;
  border-radius: 0.375rem;
  outline: none;
  background-color: blue;
  left: -4px;
  top: -4px;
  z-index: 2;
  transition:0.1s ease-in-out ;
  text-transform: uppercase;
}
a:hover {
    color: white;
    background-color: black;
    /*transform: translateY(2px) ;*/
    box-shadow:0 0 0 ;
    
}
@media screen and (max-width: 400px) {
    .container {
        justify-content: flex-start;
    }
    a {
            width: auto;
            margin: 0 auto;
        }
}
</style>