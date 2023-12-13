<script>
  import { prevent_default } from "svelte/internal";
	import FeedBackList from "./components/FeedBackList.svelte";
	import FeedbackStats from "./components/FeedbackStats.svelte";
	import FeedbackForm from "./components/FeedbackForm.svelte";






</script>

<main class="container">
	<FeedbackForm/>
	<FeedbackStats/>
	<FeedBackList/>
</main>