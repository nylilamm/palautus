<script>
    import Router, {push} from "svelte-spa-router"
    import Users from "./users.svelte";
    import Tasks from "./tasks.svelte";

    const routes = {
        "/users": Users,
        "/tasks": Tasks,

    }



</script>

<body>
<h1>Ennakkotehtävä</h1>


<nav>
    <a href="/#/users">Käyttäjät</a>
    <a href="/#/tasks">Taskit</a>
</nav>


<Router {routes} />
</body>

<style>

    h1 {
        color: #C1AFA5;
        font-family: Garamond, serif;
        font-size: 160px;
        font-weight: normal;
        letter-spacing: -6.5px;
        overflow-wrap: break-world;
        text-shadow: 0px 0px 10px rgba(255, 255, 255, 0.7);
        text-align: center;

    }

    body {
        background: linear-gradient(-45deg, #F5F2EC, #D6C6BC, #F5F2EC, #D6C6BC);
        background-size: 150% 150%;
        animation: gradient 15s ease infinite;
        height: 100vh;
        padding: 70px;
        font-family: Arial, Helvetica, sans-serif;
        color: #81726A;
    }

    a:link, a:visited {
        margin: auto;
        background-color: none;
        text-size-adjust: 100px;
        font-size: 30px;
        font-family: Garamond, serif;
        color: white;
        padding: 14px 25px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        position: relative;
        transition: all .3s cubic-bezier(.2, 0, 0, 1);
        z-index: 1;
    
    }

    a:hover, a:active {
        background-color: #faf9f6ca;
        color: #9C8A81;
        text-shadow: none;
    }


</style>