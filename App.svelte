<!-- App.svelte -->
<script>
    // ...
  
    let scientificSubjects = ["الفيزياء", "الكيمياء", "علم الأحياء", "الجيولوجيا", "علم الفلك"];
    let selectedSubject = "الكيمياء"; // المادة العلمية المحددة افتراضيًا
  </script>
  
  <select bind:value={selectedSubject}>
    {#each scientificSubjects as subject}
      <option value={subject}>{subject}</option>
    {/each}
  </select>


<main>
    <h1>تطبيق التجارب العلمية</h1>
  
    <label for="subjectSelect">اختر المادة العلمية:</label>
    <select id="subjectSelect" bind:value={selectedSubject}>
      {#each scientificSubjects as subject}
        <option value={subject}>{subject}</option>
      {/each}
    </select>
    <main>
        <h1>تطبيق التجارب العلمية</h1>
      
        <label for="subjectSelect">اختر المادة العلمية:</label>
        <select id="subjectSelect" bind:value={selectedSubject}>
          {#each scientificSubjects as subject}
            <option value={subject}>{subject}</option>
          {/each}
        </select>
      
        {#each experiments as experiment}
          {#if experiment.scientificSubject === selectedSubject || selectedSubject === "الكل"}
            <Experiment {...experiment} />
          {/if}
        {/each}
</main>

<button on:click={chooseRandomExperiment}>اختيار عشوائي</button>
<script>
    // ...
  
    function chooseRandomExperiment() {
      const randomIndex = Math.floor(Math.random() * experiments.length);
      const randomExperiment = experiments[randomIndex];
      selectedSubject = randomExperiment.scientificSubject; // تحديث المادة العلمية المحددة
    }
  </script>
  