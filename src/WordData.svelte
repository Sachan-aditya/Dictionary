<script>


</script>
<style></style>
<div class="word-data">
    {
        #if wordData.phonetics
    }
    <div class="audios">
    {#each wordData.phonetics as data}
    <div class="audios">
        <p>{
            data.text}
            <i class ="fa fa .play-circle" on on:click={()=>playAudio(data.audio)}></i></p>
    </div>
    {/each}
    </div>
    {
        /if
    }
</div>