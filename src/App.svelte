<script>
 import Loader from "./Loader.svelte";
 let  word="";
 let loading=false;
 let wordData=null;
  async function searchWord(){
	if(word.length==0)
	{
		return ;
	}
	loading=true;
	word=null;
	try{
   let res= await
	}
	catch(err){
		loading =false;
	}
  }


</script>
<style></style>
<main></main>