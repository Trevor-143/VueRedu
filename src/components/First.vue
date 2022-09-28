<template>
    <div class="backdrop" @click.self="removeModal">
        <div class="modal" :class="{ sale: theme === 'dark' }">
            <h1>The Title</h1>
            <!-- <h1>{{ header }}</h1>
            <h1>{{ two }}</h1>
            <p>
                Lorem ipsum, dolor sit amet consectetur 
                adipisicing elit. Obcaecati vero eius 
                doloremque facilis dolore eum fugiat, 
                labore numquam distinctio possimus saepe 
                voluptas sequi accusantium suscipit sit 
            </p> -->
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
            <button @click.self="removeModal">Bye</button>
        </div>
    </div>
</template>

<script>
    export default {
        props:["theme"],
        methods: {
            removeModal() {
                this.$emit('removeModal');
            }
        }
    }
</script>



<style scoped>
    body {
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .modal {
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: #ffffff;
        border-radius: 40px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    .backdrop {
        top: 0;
        position: fixed;
        background: rgba(0, 0, 0, 0.5);
        width: 100%;
        height: 100%;
    }
    
    h1 {
        color: rgb(30, 21, 153);
        border: none;
        padding: 10px 20px;
        margin: 7px;
        border-radius: 10px;
        width: fit-content;
    }
    .modal.sale {
        background: rgb(168, 174, 255);
    }
    button {
        margin: 20px;
    }
</style>