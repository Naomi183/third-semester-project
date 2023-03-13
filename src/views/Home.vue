<template>
    <div class="welcome" >
        <div class="hero">
            <h1>
                    Check out our store!
                </h1>
            <RouterLink to="/login">
                shop now
            </RouterLink>
        </div>
        <div>
            <img src="../assets/background.jpg" alt="image" />

        </div>

            
                
        
    </div>

    
</template>

<style scoped>
    .welcome {
        background-color: black;
        color: white;
        display: grid;
        grid-template-columns: repeat(2,1fr);
        width: 100%;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        min-height: 75vh;
    }
    .hero {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
       margin: 4rem;
    }
    h1 {
        font-weight: 200;
    }
    img {
        width: 100%;
    }
    a {
  text-decoration: none;
  font-size: 1.5rem;
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
    background-color: rgb(52, 52, 255);
    /*transform: translateY(2px) ;*/
    box-shadow:0 0 0 ;
    
}

@media screen and (max-width: 400px) {
        .welcome {
            display: flex;
            align-items: center;
            flex-direction: column;
            justify-content: center;
            text-align: center;
        }
        .hero {
            margin: 2rem;
        }
        h1 {
            font-weight: 300;
        }
        a {
            width: auto;
            margin: 0 auto;
        }
    }

    @media screen and (max-width: 800px) {
        .welcome {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 100%;
        }
    }
</style>