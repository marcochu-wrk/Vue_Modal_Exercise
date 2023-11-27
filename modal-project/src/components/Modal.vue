<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{aboveAge: age > 15}">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
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
.modal .actions{
    text-align: center;
    margin: 30px 0 10px 0;
}
.modal .actions a{
    color: white;
    padding: 8px;
    border: 1px solid white;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}

</style>