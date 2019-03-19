<template>
    <div class="second">
        {{msg}}
        <p>
            <router-link to="/first">to first page</router-link>
        </p>
    </div>
</template>

<script>
    export default {
        name: "second",
        data() {
            return {
                msg:"seconde page"
            }
        }
    }
</script>

<style >

</style>
