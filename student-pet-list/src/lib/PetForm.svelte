<script>
    import { roster } from "./roster.svelte.js";

    let studentName = $state("");
    let petName = $state("");
    let petType = $state("Cat");

    function addStudent(event) {   // Adds a new student and their pet to the shared roster
        event.preventDefault();

        if (!studentName.trim() || !petName.trim()) return;

        roster.students.push({
            studentName: studentName.trim(),
            petName: petName.trim(),
            petType,
        });

        studentName = "";
        petName = "";
        petType = "Cat";
    }
</script>

<form onsubmit={addStudent}>
    <h2>Add a Student and Pet</h2>

    <label>
        Student Name
        <input bind:value={studentName} required />
    </label>

    <label>
        Pet Name
        <input bind:value={petName} required />
    </label>

    <label>
        Pet Type
        <select bind:value={petType}>
            <option>Cat</option>
            <option>Dog</option>
            <option>Fish</option>
            <option>Other</option>
        </select>
    </label>

    <button type="submit">Add to Roster</button>
</form>
