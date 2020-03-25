<script>


	import { onMount } from 'svelte';

    //adapted from https://codepen.io/gavra/pen/tEpzn

    let aText = new Array(
        "Hi :) I'm <span class='n'>Jit</span> this is my site!",
        "", 
        "I studied software engineering and worked as a .Net Developer for a little bit.",
        "",
        "Then, I decided to change routes and become a cyber consultant.",
        "",
        "I specialise in creating innovative technical solutions to everyday business problems.", 
        "",
        "You can explore my skills and expertise below!",
        );

    let iSpeed = 100; // time delay of print out
    let iIndex = 0; // start printing array at this posision
    let iArrLength = aText[0].length; // the length of the text array
    let iScrollAt = 20; // start scrolling up at this many lines
        
    let iTextPos = 0; // initialise text position
    let sContents = ''; // initialise contents variable
    let iRow; // initialise current row
        
    function typewriter()
    {
        sContents =  ' ';
        iRow = Math.max(0, iIndex-iScrollAt);
        let destination = document.getElementById("typedtext");
        while ( iRow < iIndex ) {
            sContents += aText[iRow++] + '<br />';
        }
        destination.innerHTML = sContents + aText[iIndex].substring(0, iTextPos) + "<span class='u'>_</span>";
        if ( iTextPos++ == iArrLength ) {
            iTextPos = 0;
            iIndex++;
            if ( iIndex != aText.length ) {
                iArrLength = aText[iIndex].length;
                setTimeout(typewriter, 500);
            }
        } 
        else {
            setTimeout(typewriter, iSpeed);
        }
    }

    onMount(async () => {
        typewriter()
    });

</script>

<h5 id="typedtext"></h5>

<style>
    
    :global(.n) {
        background-image: linear-gradient(120deg, rgb(245, 88, 93) 0%, rgb(243, 84, 40) 100%);
        background-repeat: no-repeat;
        background-size: 100% 0.3em;
        background-position: 0 100%;
        transition: background-size 0.25s ease-in;
    }

    :global(.u){
        background: -webkit-linear-gradient(120deg, rgb(245, 88, 93) 0%, rgb(243, 84, 40) 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        animation:blinkingText 1.2s infinite;
    }
    #typedtext{
        font-size: 1.25rem;
        font-weight: bold;
    }
</style>