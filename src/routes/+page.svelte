

<div id="title">
<h1>Figma Components
</h1>
</div>


<style>

   *{
    overflow: hidden;
   }
    #title{
        width: 100vw;
        height: fit-content;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    #title h1{
        font-family: "Inter", sans-serif;
        font-size: 4rem;
        position: relative;
        padding-bottom: 2vh ;
        user-select: none;
        
    }

    #title h1::after{
           content: '';
           width: 100%;
           height: 7%;
           position: absolute;
           background-color: black;
           border-radius: 20px;
           left: 0;
           bottom: 2%;
    }
</style>