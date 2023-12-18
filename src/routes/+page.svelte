<script>
    let paragraph = "lets see";
    function handleSend(){
        let resultArea = document.getElementById("resultArea");
        let resultText = "not yet implemented";
        if (resultArea) resultArea.value   
        += "You:" + paragraph + "\n" 
        + "Overstand: " + resultText + "\n"
        + "---------" + "\n";
        let resultsCanvas = document.getElementById("resultsCanvas");
        if (resultsCanvas) resultsCanvas.getContext("2d").fillText(paragraph, 10, 10);
        paragraph = "";
    }

	function handleClear() {
		let resultArea = document.getElementById("resultArea");
        if (resultArea) resultArea.value = "";
        paragraph = "";
	}

    function handleKeydown(event) {
        if (event.key === 'Enter') {
            handleSend();
        }
    }
</script>

<h1>Welcome to SvelteKit Overstand</h1>
<!-- <p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p> -->
Please enter your text

<input type="text" id="textInput" bind:value={paragraph} on:keydown={handleKeydown} />
<br />

<button id="sendBtn" on:click={handleSend}>Send</button> &nbsp;&nbsp; 
<button id="clearBtn" on:click={handleClear}>Clear</button>
<hr />
<textarea name="resultArea" id="resultArea" cols="30" rows="10"></textarea>
<hr />
<canvas id="resultsCanvas"></canvas>