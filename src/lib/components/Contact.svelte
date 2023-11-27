<script>

  import { onMount } from "svelte";

  onMount(() => {

  console.log(data)

  });

export let data
  
</script>


<section class="contact section" id="experience">
  <h2>Contact</h2>
  <p>Voel je vrij om contact met ons op te nemen</p>

<div class="main-container">

<form action="mailto:maaike.verplancke@hotmail.com" method="post" enctype="text/plain">
        <label for="name">Voor- en achternaam*</label>
        <input type="text" id="name" name="name" required placeholder="Jan dekkers">

        <label for="email">E-mail*</label>
        <input type="email" id="email" name="email" required placeholder="Jandekkers@hotmail.com">

        <label for="message">Notitie*</label>
        <textarea id="message" name="message" rows="4" required placeholder="Opmerking..."></textarea>
        <button type="submit" onclick="sendEmail()">Verstuur</button>
    </form>
  <img src="assets/tree.png" alt="afbeelding boom naast invulformulier">

</div>
</section>

<style>
img{
  width: 90%;
}

h2{
    padding-top: 2rem;
    color: var(--spat);
  }

p {
    margin-bottom: 1rem;
    color: var(--darkblue);
    font-size: 0.8rem;
}

/* FORMULIER */
form{
    display: flex;
    flex-direction: column;
    justify-content: center;
}

input, textarea{
    container: inline-size;
}

.main-container{
  container: sidebar / inline-size;
  display: grid;
  grid-template-columns: 1fr 1fr;
}

@container sidebar (min-width: 700px) {
img{
  margin-left: 2em;
}
}

@container sidebar (max-width: 700px) {
img{
  display: none;
}
.main-container{
  container: sidebar / inline-size;
  display: grid;
  grid-template-columns: 1fr;
}
}


/* @container (max-width: 400px) { */


label{
    margin-top: 1rem;
    margin-bottom: .5rem;
    color: var(--darkblue);
    font-size: 0.8rem;
}

input, textarea{
  width: 100%;
  height: 45px;
  padding: .7em;
  border-color: #CCCCCC;
  border-top: #CCCCCC;
  border-left: #CCCCCC;
  border-radius: 10px;
  border-width:1px;
}

input:focus,
textarea:focus {
  opacity: 1;
  border-radius: 10px;
  border: 10px;
  transform: scale(1.01, 1.01);
  outline: none;
  box-shadow: 0 0 0 2px var(--darkblue);
}

input::placeholder,
textarea::placeholder{
  opacity: 80%;
  color:#CCCCCC;
  font-style: italic;
}

button {
    display: inline-block;
    background-color: var(--green);
    color: white;
    padding: 0.5rem 1rem;
    margin-top: 2em;
    border-radius: 5px;
    font-weight: var(--font-semi-bold);
    transition: 0.3s;
    text-decoration: none;
    width: 100px;
    border: none;
}

  .contact {
    padding: 4rem 5rem;
    height: auto;
    background-color: var(--lg-bg);
  }


</style>
