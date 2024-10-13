<script script lang="ts">
    export let title: string;
    export let content: string;
    export let onSubmit: (title:string, contect:string) => void;

</script>

<div class="containter">
    <p>Title </p>
    <input type="text" bind:value={title} />
    <p>Content</p>
    <input type="text" bind:value={content} />
    <button on:click={()=>onSubmit(title, content)}>save</button>
</div>