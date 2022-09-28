<template>
    <div class="backdrop" @click.self="removeModal2">
        <div class="modal" :class="{ sale: theme === 'darksss' }">
            <h1>The Title</h1>
            <slot></slot>
            <div class="actions">
                <slot name="likes"></slot>
            </div>
            <button @click.self="removeModal2">Bye</button>
        </div>
    </div>
</template>

<script>
    export default {
        props:["theme"],
        methods: {
            removeModal2() {
                this.$emit('removeModal2');
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
        background: #bddfff;
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