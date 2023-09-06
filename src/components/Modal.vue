<script setup>

defineProps({
    header: null, 
    body: null, 
    theme: null,
    show: Boolean,
    hideFunction: [Function, undefined]
});
const emit = defineEmits(['close'])

const hideFromChild = () => {
    emit('close')
}

</script>

<template>
    <teleport to=".modals" v-if="show">
        <div class="backdrop" @click="hideFromChild()">
            <div class="modal" :class="theme" @click.stop>
                <h1>{{ header ?? "" }}</h1>
                <hr>
                <p>{{ body.line1 }}</p>
                <div>
                    <slot name=""></slot>
                    <slot name="links"></slot>
                </div>
            </div>
        </div>   
    </teleport> 
</template>

<style scoped>
.modal{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}
.backdrop{
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
}
h1{
    color: aquamarine;
    font-size: 2em;
}
</style>