<script>
  import { prevent_default } from "svelte/internal";
	import FeedBackList from "./components/FeedBackList.svelte";
	import FeedbackStats from "./components/FeedbackStats.svelte";
  let feedback = [
  {
    id: 1,
    rating: 10,
    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
  },
  {
    id: 2,
    rating: 9,
    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
  },
  {
    id: 3,
    rating: 8,
    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
  },
];

const deleteFeedback = (e)=>{
	const itemId = (e.detail)
	feedback = feedback.filter((item) => item.id != itemId)
}

$: count = feedback.length;
$:average = feedback.reduce((prev, current)=>{
	return prev += current.rating;
}, 0) / count;

</script>

<main class="container">

	<FeedbackStats {count} {average}/>
	<FeedBackList feedback={feedback} on:delete-feedback={deleteFeedback}/>
</main>