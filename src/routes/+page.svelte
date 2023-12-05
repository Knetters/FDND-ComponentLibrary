<script>
  export let data
  import { onMount } from 'svelte';

  import Home from "../lib/components/Home.svelte"
  import Over from "../lib/components/Over.svelte"
  import Expertise from "../lib/components/Expertise.svelte"
  import Klimaatadaptatie from "../lib/components/Klimaatadaptatie.svelte"
  import Waterkwaliteit from "../lib/components/Waterkwaliteit.svelte"
  import Brain from "../lib/components/Brain.svelte"
  import Projecten from "../lib/organisms/Projecten.svelte"
  import Kennisbank from "../lib/components/Kennisbank.svelte"
  import Team from "../lib/components/Team.svelte"
  import Contact from "../lib/components/Contact.svelte"
  import Partners from "../lib/components/Partners.svelte"
  import Footer from "../lib/components/Footer.svelte"

  onMount(() => {
    function clickEffect(e) {
  var clickDiv = document.createElement("div");

  clickDiv.className = "clickEffect";
  clickDiv.style.top = e.clientY + "px";
  clickDiv.style.left = e.clientX + "px";

  document.body.appendChild(clickDiv);
  
  clickDiv.onanimationend = function() {
    clickDiv.parentElement.removeChild(clickDiv);
  };
}

document.addEventListener("click", clickEffect);
  });

</script>

  <Home />
  <Over {data} />
  <Expertise />
  <Klimaatadaptatie {data} />
  <Waterkwaliteit />
  <Brain />
  <Projecten {data} />
  <Team {data} />
  <Contact />
  <Partners {data} />
  <Footer />

<style>
  
</style>