<script context="module">
    export async function load({fetch}) {
        const res = await fetch(`https://api.themoviedb.org/3/movie/popular?api_key=0c19aa790ef3cb44ca6a74ec51a4e97c&language=en-US&page=1`)
       
        const data = await res.json()

        console.log(data)

        if(res.ok) {
            return {
                props: {popular: data.results}
            }
        }
   }
</script>

<script>
    import PopularMovies from "../components/PopularMovies.svelte";
    export let popular
</script>

<section>
    <PopularMovies {popular}/>
</section>