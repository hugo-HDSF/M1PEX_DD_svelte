<script>
  import App from './App.svelte';

  export let question;
  export let onToggle;

  function handleKeydown(event) {
    if (event.key === 'Enter') {
      onToggle();
    }
  }
</script>

<style>
    /* Votre CSS ici */
</style>

<div class="card"
     on:click={onToggle}
     role="button"
     tabindex="0"
     on:keydown={handleKeydown}>
    <div class="question-number">
        <h3>{@html question.number}
        <span class="toggle-icon">{question.isOpen ? '▲' : '▼'}</span></h3>
    </div>
    <!-- Ajouter role="button" et tabindex="0" pour rendre le div accessible -->
    <div class="question-title">
        <h4>{question.title}</h4>
    </div>
    <div class={question.isOpen ? 'answer open' : 'answer'}>
        {@html question.content}
    </div>
</div>
