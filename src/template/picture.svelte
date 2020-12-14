<script>
    import { bool2 } from '../store/store.js'
    export let img 
    export let float
    let imgbck = "url('https://media3.giphy.com/media/WZrOaNjFPKT5e/giphy.gif')"
    
$: if ($bool2) {
    imgbck = "url('data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBw8PDw0PDw0NDQ0NDQ0NDQ0NDQ8NDQ8PFREWFhURFRUYHSggGBolHRUVITEhJSkrLi4uFx8zODMtNygtLisBCgoKDQ0NDg0NDisZFRkrKy03LS03Ky0tKys3LSs3Ky0rLS0tLSsrNys3KysrKysrLSsrLSsrNysrKysrKysrK//AABEIAOEA4QMBIgACEQEDEQH/xAAXAAEBAQEAAAAAAAAAAAAAAAAAAQIH/8QAFhABAQEAAAAAAAAAAAAAAAAAAAER/8QAFQEBAQAAAAAAAAAAAAAAAAAAAAH/xAAVEQEBAAAAAAAAAAAAAAAAAAAAAf/aAAwDAQACEQMRAD8A4eIoAAAAAAAAAAAAAACKAAAAAAgAAAAAAKCAoAAAAAAAIoAAAAAAAIoAAAgAAAKgCiAKBAAAAAAAAAAAAARQAAAAAAAAAABAUEFAAAAAAAAAAAFQAAAAAAAAAAARQAEABQAAAAAAAAAIAACKUAAAAAAAAAAA0AAAEUQFEAUAAAAAAAAAAAAFBAAFRQQAAABFQAUAQUAAAACAAAAAAAAAACooKggqKKiCoihAAAAABFEBQAAAAAAAAAAUEAAFQAAFEAVAAAARQEUARQAAAAAAAAAAAAUFQBUAoAIAAAAAAAICgAiooAAAAAAAAAICkAAAAAFQVRAAAEAABFQFABAUEFAAAAARQAAAAAIAACgrKoKgKACAAAAACAqKgKIAoAAAAAAAAAAAAAAAAAAAAACLQBFQBUAUQAUAAAAAAAAVUQRUUVBQqoIAAAAIKAIoAACAoAAAYAAAAAAAAAAAAAAAAACKAIoCAAAACgaACoCioAACAgAoAEAAgAAAFFFoyoIJVACkABAAoAKAD//Z')";
    console.log("bruh");
} else{
    imgbck = "url('https://media3.giphy.com/media/WZrOaNjFPKT5e/giphy.gif')"
}
</script>
<img src = "{img}" alt = "img" style="--background: {imgbck}; --float: {float}"/>
<style>
    img{
        background-image: var(--background);
        padding: 8px;
        border: 1px solid black;
        height: 250px;
        float: var(--float);
        display: block;
        margin: 5px;
        margin-top: -58px;
    }
</style>