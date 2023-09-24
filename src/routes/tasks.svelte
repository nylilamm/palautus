<script>

    let users = [];
    let selectedUser;


    fetch('https://jsonplaceholder.typicode.com/users')
    .then(response => response.json())
    .then(json => {
    users = json;
    console.log(json)
    })
    

    let todos = []


    async function findTodos(e) {
        fetch(`https://jsonplaceholder.typicode.com/todos?userId=${selectedUser}`)
        .then(response => response.json())
        .then(json => {
        todos = json;
    })
    }


</script>

<p>Valitse käyttäjä kenen taskeja haluat tarkastella:</p>

<select bind:value={selectedUser} on:change={findTodos}>
    <option>Valitse käyttäjä</option>
    {#each users as user}
    <option value="{user.id}">{user.name}</option>
    {/each}
</select>

<p></p>

{#if todos.length}
    <table>
        <tr><th>ID</th><th>Otsikko</th><th>Suoritettu</th></tr>
        {#each todos as todo}
        <tr><td>{todo.id}</td><td>{todo.title}</td><td>{todo.completed}</td>
        {/each}
    </table>
{/if}


<style>

    select{
        width: 30%;
        height: 40px;
        border: 1px solid #ccc;
        border-radius: 5px;
        padding-left: 5px;
        padding: 8px;
        font-size: 14px;
        font-family: 'Open Sans', sans-serif;
        color: #555;
        background-color: rgba(255, 255, 255, 0.659);
        background-image: none;
        border: 1px solid rgb(41, 18, 18);
    }

    select>option{
        font-size: 14px;
        font-family: 'Open Sans', sans-serif;
        color: #555;
        background-color: rgba(247, 247, 247, 0.553);
        background-image: none;
        font-size: 18px;
        height: 40px;
        padding: 15px;
        border: 1px solid rgb(41, 18, 18);

    }

    P {
        font-family: Arial, Helvetica, sans-serif;
        color: #8E7D75;
    }

    table {
        font-family: Arial, Helvetica, sans-serif;
        color: #8E7D75;

    }

    th {
        font-family: Garamond, serif;
        font-size: 25px;
        text-align: left;
        color: white;
    }

</style>
