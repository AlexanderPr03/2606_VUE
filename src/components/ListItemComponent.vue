<template>
    <div class="card">
        <h2>{{ titluProdus }}</h2>
        <p>{{ pretProdus }}</p>

        <p>{{ counter }}</p>

        <!-- Event listeners in forma prescurtata in Vue -->
        <button @click="notifyParentIncrement">Increment</button>
        <button @click="notifyParentDecrement">Decrement</button>
    </div>

</template>

<script>
export default {
    name:'ListItemComponent',
    // Properties
    // props:['titluTask','descTask']
    props: {
        titluProdus: {
            type: String,
            default: 'Titlu General Produs'
        },
        pretProdus: {
            type: String,
            default: 'Descrierea generala a produsului'
        }
    },
    // Optiunea care ne permite să creăm în interiorul componentului
    data() {
        return {
            counter:0,
            data: new Date,

        }
    },
    // methods: Stocarea funcțiilor interne ale componentului
    methods: {
        incrementCounter() {
            this.counter++;
        },
        decrementCounter() {
            this.counter--;
        },
        notifyParentIncrement() {

            this.incrementCounter();
            // $ - metoda/variabila globala
            // $emit() - metoda globala care ne permite sa emitem evenimente personalizate
            this.$emit('counterUpdatedPlus');
        },
        notifyParentDecrement() {

            this.decrementCounter();
            // $ - metoda/variabila globala
            // $emit() - metoda globala care ne permite sa emitem evenimente personalizate
            this.$emit('counterUpdatedMinus');
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