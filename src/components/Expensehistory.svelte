<script>
import Card from "../../../my-svelte-project/src/components/Card.svelte";
import App from "../App.svelte";

    
    export let transactions = []

</script>

{#each transactions as transaction (transaction.id)}
    <div class="transaction_card">
        <span class="name">{transaction.name}</span> 
        <span class="value">{transaction.value}</span>
    
    </div>
{/each}

<style>
    .transaction_card {
        background-color: white;
        border: 2px;
 		border-radius: 10px;
        padding: 1vw;
        margin-top: 1vh;
        text-align: end;
    }

    .name {
        display: inline;
        float: left;

    }

    .value {
        display: inline;
        text-align: right;
        

    }

</style>