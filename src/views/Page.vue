<template>
    <div id="page">
        <logout-button></logout-button>
        <tweet-form></tweet-form>
        
    </div>
</template>
<script>
import TweetForm from '../components/TweetForm.vue'
import LogoutButton from '../components/LogoutButton.vue';
export default {
    name: 'Page',
    components: { LogoutButton, TweetForm },
    computed: {
        token() {
            return this.$store.state.token;
        }
    },
    created() {
        if(this.token) {
            this.router.push({ name: 'login' });
        }
    }
    
}
</script>