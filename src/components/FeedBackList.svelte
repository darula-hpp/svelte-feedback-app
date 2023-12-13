<script>
    import { onMount, onDestroy } from 'svelte';
    import {FeedbackStore} from '../stores'
    import { fade, scale } from "svelte/transition";
    import FeedbackItem from "./FeedbackItem.svelte";

</script>

{#each $FeedbackStore as item (item.id)}
<div in:scale out:fade>
    <FeedbackItem item={item} on:delete-feedback/>
</div>

{/each}