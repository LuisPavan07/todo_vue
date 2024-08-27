<script setup>
    const props = defineProps(['tarefas']);
</script>
<template>
    <ul v-if="props.tarefas.length > 0" class="list-group mt-5">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
    <p v-else class="mt-5 ms-2">Não há tarefas pendentes!</p>
</template>
<style scoped>
    .done {
        text-decoration: line-through
    }
</style>