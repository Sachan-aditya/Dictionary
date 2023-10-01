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
    {
    #each wordData.meanings as meaning
    }
    <div class="meaning">
        <div class="part-of-speech">&bull; {meaning.partofSpeech}</div>
        <div class="definitions">
            {
            #each meaning.definitions as data
            }
            <div class="definitions">
                <p>Definitions:<b>{data.definitions}</b></p>
                {#if data.example}
            <p>Example:</p>
                {/if}
            </div>
            {
                /each
            }
        </div>
    </div>
    {/each}
</div>
