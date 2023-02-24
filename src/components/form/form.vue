<template lang="">
    <form  @submit.prevent class=" d-flex gap-3 mt-3 flex-column">
        <input  @:input="name = $event.target.value" type="text" :value="name" placeholder='Todo nomini yozing' class="form-control">
        <select @:input="status = $event.target.value" :value="status" class='form-select'>
            <option value="true">Bajarilgan</option>
            <option value="false" selected>Qilinmagan</option>
            <option value="sleep">Bajarilmoqda</option>
        </select>
        <input  @click="newTodo"  type="button" value="Add" class='btn btn-primary w-100 m-auto'>
    </form>
</template>

<script>
export default {
    data(){
        return {
            name: '',
            status: 'false'
        }
    },
    methods: {
        newTodo(e){
            e.preventDefault();
            const newTodo = {
                name: this.name,
                status: this.status
            }
            this.name = ''
            this.status = 'false'
            this.$emit("addTodo", newTodo)  
        },
        editTodo(e){
            console.log('Work');
        }
    },
}
</script>
<style>



</style>