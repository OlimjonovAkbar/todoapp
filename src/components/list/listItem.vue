<template lang="">
    <li class='list-item rounded text-black'>
        <span>{{todo.name}}</span>
        <div class="buttons d-flex items-center gap-2">
            <span v-if="todo.status == 'true'" class='status rounded-circle bg-success'></span>
            <span v-else-if="todo.status == 'false'" class='status rounded-circle bg-danger'></span>
            <span v-else-if="todo.status == 'sleep'" class='status rounded-circle bg-warning'></span>
            <button @click="$emit('onEdit', {id: todo.id})" class="btn btn-primary"><i class="fa fa-pencil" aria-hidden="true"></i></button>
            <button @click="$emit('onRemove', {id: todo.id})" class="btn btn-danger"><i class="fa fa-trash" aria-hidden="true"></i></button>
        </div>
    </li>
</template>

<script>
export default {

    props:{
        todo:{
            type:Object,
            required: true,
        }
    },

}
</script>
<style scoped>
    .status{
        width: 30px;
        height: 30px;
    }
</style>