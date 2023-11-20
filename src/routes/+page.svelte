<script>
  export let data

  import Navbar from "../lib/components/Navbar.svelte";
  import Home from "../lib/components/Home.svelte";
  import Over from "../lib/components/Over.svelte";
  import Expertise from "../lib/components/Expertise.svelte";
  import Klimaatadaptatie from "../lib/components/Klimaatadaptatie.svelte";
  import Waterkwaliteit from "../lib/components/Waterkwaliteit.svelte";
  import Brain from "../lib/components/Brain.svelte";
  import Projecten from "../lib/components/Projecten.svelte";
  import Kennisbank from "../lib/components/Kennisbank.svelte";
  import Team from "../lib/components/Team.svelte";
  import Contact from "../lib/components/Contact.svelte";
  import Partners from "../lib/components/Partners.svelte";
  import Footer from "../lib/components/Footer.svelte";
</script>

<Navbar />
<Home />
<Over />
<Expertise />
<Klimaatadaptatie />
<Waterkwaliteit />
<Brain />
<Projecten {data} />
<Kennisbank {data} />
<Team {data} />
<Contact />
<Partners {data} />
<Footer />
