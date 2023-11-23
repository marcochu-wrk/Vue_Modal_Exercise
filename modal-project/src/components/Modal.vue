<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{aboveAge: age > 15}">
            <h1>{{header}}</h1>
            <p>{{ text }}</p>
            <p>{{ age }}</p>
        </div>
    </div>
</template>

<script>
export default{
    props:['header','text', 'age'],
    methods:{
        closeModal(){
            this.$emit('close')
        }
    }
}
</script>
<!-- Not every style needs to be scoped to be its own instance, can just be more specific eg. .modal h1 -->
<style>
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
    background: rgba(0, 0, 0, 0.247);
    width: 100%;
    height: 100%;
}
.modal h1{
    color: black;
}
.modal.aboveAge{
    background-color: crimson;
    color: white;
}
.modal.aboveAge h1{
    color: white;
}
</style>