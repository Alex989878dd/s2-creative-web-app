<script>
  import './classless.css';
  import PetForm from './lib/PetForm.svelte';
  import PetList from './lib/PetList.svelte';
</script>

<main>
  <h1>Student Pet Roster</h1>
  <p>Add students and their pets to the list.</p>
  <PetForm />
  <PetList />
</main>
