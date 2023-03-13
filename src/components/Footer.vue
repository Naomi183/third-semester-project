<template>
    <div class="footer">
        <small> Proudly sponsored by <a href='https://github.com/Ahmad-Zahradeen-Tahir' target='_blank'>Zaheer Tech</a> &copy; {{ date }}</small>
        
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
        color: white;
        background-color: black;
        margin-top: auto;
    }
    small {
        margin: 0 1rem;
    }
</style>