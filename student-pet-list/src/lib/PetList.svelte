<script>
    import { roster } from "./roster.svelte.js";
</script>

<section>
    <h2>Students and Pets</h2>

    <output>{roster.students.length} students registered</output>

    {#if roster.students.length === 0} <!-- Show a message when the roster is empty, otherwise list all students and pets -->
        <p>No students yet.</p>
    {:else}
        <ul>
            {#each roster.students as student}
                <li>
                    <strong>{student.studentName}</strong>
                    — {student.petName} ({student.petType})
                </li>
            {/each}
        </ul>
    {/if}
</section>
