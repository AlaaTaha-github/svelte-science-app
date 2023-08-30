<!-- Experiment.svelte -->
<script>
    export let title;
    export let description;
    export let materials;
    export let instructions;
    export let safetyPrecautions;
    export let scientificExplanation;
  </script>
  
  <div class="experiment">
    <h2>{title}</h2>
    <p>{description}</p>
    
    <h3>المواد المطلوبة:</h3>
    <ul>
      {#each materials as material}
        <li>{material}</li>
      {/each}
    </ul>
    
    <h3>التعليمات:</h3>
    <ol>
      {#each instructions as step}
        <li>{step}</li>
      {/each}
    </ol>
    
    <h3>تدابير السلامة:</h3>
    <p>{safetyPrecautions}</p>
    
    <h3>الشرح العلمي:</h3>
    <p>{scientificExplanation}</p>
  </div>
  