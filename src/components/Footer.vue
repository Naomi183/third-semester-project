<template>
    <div class="footer">
        <small> Proudly sponsored by <a href='https://github.com/Naomi183' target='_blank'>Naomi CO</a> &copy; {{ date }}</small>
        
    </div>
</template>
<script>
export default {
    setup(){

        const date = new Date().getFullYear()
        return {
            date
        }
    }
}

</script>
<style>
    .footer {
        display: flex;
        align-items: center;
        justify-content: center;
        color: beige;
        background-color: black;
        margin-top: auto;
    }
    small {
        margin: 0 1rem;
    }
</style>