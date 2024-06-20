<template>
    <div class="card">
        <h2>{{ titluTask }}</h2>
        <p>{{ descTask }}</p>
    </div>

</template>

<script>
export default {
    name:'ListItemComponent',
    // Properties
    // props:['titluTask','descTask']
    props: {
        titluTask: {
            type: String,
            default: 'Titlu General Task'
        },
        descTask: {
            type: String,
            default: 'Descrierea generala a taskului'
        }
    }
}

</script>


<style>
.card {
    width: 300px;
    height: auto;
    border: 1px solid black;
    border-radius: 12px;
}
</style>