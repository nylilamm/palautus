<script>
    let users = []

    fetch('https://jsonplaceholder.typicode.com/users')
        .then(response => response.json())
        .then(json => {
        console.log(json)

        users = json
        console.log(users[0].name)
    })

</script>

<p></p>
<p></p>

<table>
    <tr><th>Nimi</th><th>Käyttäjä</th><th>Sähköposti</th><th>Osoite</th><th>Puhelin</th><th>Kotisivut</th></tr>
        {#each users as user}
            <tr>
            <td>{user.name}</td>
            <td>{user.username}</td>
            <td>{user.email}</td>
            <td>{user.address.street}, {user.address.suite}, {user.address.city}, {user.address.zipcode}</td>
            <td>{user.phone}</td>
            <td>{user.website}</td>
            </tr>
    {/each}
</table>

    
<style>

    th {
        font-family: Garamond, serif;
        font-size: 25px;
        text-align: left;
        color: white;
        
    }

    td {
        font-family: Arial, Helvetica, sans-serif;
        color: #8E7D75;

    }

    P {
        font-family: Arial, Helvetica, sans-serif;
        color: #8E7D75;
    }


</style>