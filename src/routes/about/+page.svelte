<main>
    <h1>Привет, мир! меня зовут Кирилл.</h1>
    <h1>Мне 16 лет, я живу в городе Ижевск.</h1>
    <section>
        <h2>Навыки:</h2>
        <ul>
            <li>HTML</li>
            <li>CSS</li>
            <li>JavaScript</li>
            <li>Node.JS</li>
            <li>SveltaKit</li>
        </ul>
    </section>
    <img src={avatar} alt="мое фото" height="250px" width="500px">
</main>
<style>
main {
    display: flex;
    flex-direction: column;
    align-items: left;
    min-height: 100%;
    padding: 5vmin;
    box-sizing: border-box;
    background: antiquewhite;
    }
</style>
<script>
    import avatar from "../../components/rngsl.png"
</script>