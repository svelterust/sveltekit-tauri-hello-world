<script lang="ts">
  import { invoke } from "@tauri-apps/api/tauri";

  let name: string;
  let output: string;
  async function greet() {
    output = await invoke("greet", { name });
  }
</script>

<label for="name">Name:</label>
<input name="name" type="text" bind:value={name} on:change={greet} />
{#if output}
  <p>{output}</p>
{/if}
