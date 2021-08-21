<script>
    import { createEventDispatcher } from "svelte";
    const dispath = createEventDispatcher();
    export let items;
    export let activeItem;
</script>

<div class="tabs">
    <ul>
        {#each items as item}
            <li>
                <div on:click={() => dispath('tabChange',item)} class:active={item === activeItem}>{item}</div>
            </li>
        {/each}
    </ul>
</div>

<style>
    .tabs{
        margin-bottom: 40px;
    }
    ul{
        display: flex;
        justify-content: center;
        margin-bottom: 40px;
        padding: 0;
        list-style-type: none;
    }
    li{
        margin: 0 16px;
        font-size: 18px;
        color: rgb(158, 158, 158);
        cursor: pointer;
    }
    .active{
        color: #d83a5a;
        border-bottom: 2px solid #d83a5a;
    }
</style>