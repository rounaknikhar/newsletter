<template>
    <div class="card-container">
        <div class="text-side">
            <h1>Stay updated!</h1>
            <p>
                Join 60,000+ product managers receiving monthly updates on:
            </p>
            <div class="tick-list">
                <span class="list">
                    <img src="../assets/icon-list.svg" alt="list">
                    <p>Product discovery abd building what matters</p>
                </span>
                <span class="list">
                    <img src="../assets/icon-list.svg" alt="list">
                    <p>Product discovery abd building what matters</p>
                </span>
                <span class="list">
                    <img src="../assets/icon-list.svg" alt="list">
                    <p>Product discovery abd building what matters</p>
                </span>
            </div>

            <form class="send-email">
                <label for="email">Email address</label>
                <input type="email" name="email" id="email" placeholder="email@company.com" />
                <ActionButton />
            </form>
        </div>
        <div class="image-side">
            <img class="desktop" src="../assets/illustration-sign-up-desktop.svg" alt="image">
            <img class="mobile" src="../assets/illustration-sign-up-mobile.svg" alt="image">
        </div>
    </div>
</template>
  
<script>
import ActionButton from '../components/ActionButton.vue';
export default {
    name: 'App',
    components: {
        ActionButton
    }
}
</script>