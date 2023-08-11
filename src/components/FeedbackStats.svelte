<script>
    import {FeedbackStore} from '../stores'

    $: count = $FeedbackStore.length
	$: average = $FeedbackStore.reduce((acc, c) => acc + c.rating, 0) / count
</script>


<div class="feedback-stats">
    <h4>{count} Reviews</h4>
    <h4>Ratings Average: {average > 0 ? average : 0}</h4>
</div>

<style>
    .feedback-stats{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
</style>