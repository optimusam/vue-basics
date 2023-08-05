<template>
    <div class="container">
        <h1 class="title">Hello There!</h1>
        <p>We have a gift waiting for you</p>
        <button class="button btn-primary" @click="openModal(modal1)">Get First Gift!</button>
        <button class="button btn-primary" @click="openModal(modal2)">Get Second Gift!</button>
        <button class="button btn-primary" @click="openModal(modal3)">Get Slot Gift!</button>
        
        <Modal 
        :title="modal1.modalTitle" 
        :showModal="modal1.showModal"
        :content="modal1.content" 
        @close="closeModal"/>
        
        <Modal 
        :title="modal2.modalTitle" 
        :showModal="modal2.showModal"
        :content="modal2.content" 
        @close="closeModal"/>  
        
        <Modal
        :title="modal3.modalTitle" 
        :showModal="modal3.showModal"
        :content="modal3.content" 
        @close="closeModal">
            <h1 class="title">{{ modal3.modalTitle }}</h1>
            <h1 class="title">This is a Vue slot</h1>
        </Modal>
        
    </div>

</template>
<script>
    import Modal from './components/Modal.vue'
    
    export default {
        name: 'App',
        components: { Modal },
        data() {
            return {
                modal1: {
                    modalTitle: 'You have won a Lambo!',
                    content: 'Purple lamborghini',
                    showModal: false
                },
                modal2: {
                    modalTitle: 'You have won a lemon!',
                    content: 'Purple lemon!',
                    showModal: false
                },
                modal3: {
                    modalTitle: 'Now this is getting interesting...',
                    content: 'Purple Nothing!',
                    showModal: false
                },

            }
        },
        methods: {
            openModal(modal) {
                modal.showModal = true;
                console.log(`opening modal ${modal.modalTitle}`);
            },
            closeModal() {
                this.modal1.showModal = false;
                this.modal2.showModal = false;
                this.modal3.showModal = false;
            }
        }
    }
</script>
<style scoped>
</style>
