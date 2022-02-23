<script>
    import App from "../App.svelte";
    import {createEventDispatcher} from 'svelte';
    import {fade, blur } from 'svelte/transition';

    
    export let transactions = []

    const dispatch = createEventDispatcher()

    const delteTransaction = (id) => {
        dispatch('delete_transaction', id)
    }
</script>

{#each transactions as transaction , i(transaction.id)}
    <div class="transaction_card" in:blur out:fade>
        <div on:click={delteTransaction(i)} class="close">X</div>
        <span class="name"> {transaction.name}</span> 
        <span class="value"> {transaction.value}</span>
    
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
        margin-left: 1vw;
        
    }

    .value {
        display: inline;
        text-align: right;
        

    }

    .close {
        float: left;
        color: white;
        transition: color;
        -webkit-touch-callout: none;
        -webkit-user-select: none;
        -khtml-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
                
    } 

    .close:hover {
        color: black;
    }
</style>