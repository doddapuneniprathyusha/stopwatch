# stopwatch
creating a stopwatch using javascript(index.html)
<!DOCTYPE html>
<html>
    <head>
        <meta name = "viewport" content="width=device"-width,initial-scale=1.0>
        <title>stopwatch Using Javascript</title>
        <link rel ="stylesheet" href="style.css">
    </head>
    <body>
        <div class ="stopwatch">
            
                <h1 id="displaytime"> 00:00:00 </h1>
                <div class="buttons">
                    <img src="imagesstop.png" onclick="watchstop()">
                    <img src="imagesstarts.jpg" onclick="watchstart()">
                    
                    <img src="imagesreset.jpg" onclick="watchreset()">
                    
                </div>
                <script>
                    let [seconds,minutes,hours]=[0,0,0];
                    let displaytime=document.getElementById("displaytime");
                    let timer=null;
                    function stopwatch(){
                        seconds++;
                        if(seconds == 60){
                            seconds=0;
                            minutes++;
                            if(minutes == 60){
                                minutes=0;
                                hours++;

                            }
                        }
                               let h =hours < 10 ? "0" + hours : hours;
                               let m =minutes < 10 ? "0" + minutes : minutes;
                               let s =seconds < 10 ? "0" + seconds : seconds;

                        
                       
                            displaytime.innerHTML = h + ":"+ m+":" + s;

                   
        
        
                        }

                  function watchstart(){
                    if(timer!==null)
                    {
                        clearInterval(timer);
                    }
                   timer = setInterval(stopwatch,1000);
                    

                    }
                  function watchstop(){
                    clearInterval(timer);

                  }
                  function watchreset(){
                    clearInterval(timer);
                    [seconds,minutes,hours]=[0,0,0];
                    displaytime.innerHTML ="00:00:00";
                  }

 



                </script>


                styling part (style.css)
body{
    background: #edeaff
}
.stopwatch{
    width: 90%;
    max-width: 600px;
    background-image: linear-gradient(rgba(0,0,0,0.8),rgba(0,0,0,0.8))  url(https://img.freepik.com/free-photo/painting-mountain-lake-with-mountain-background_188544-9126.jpg);
    background-size: cover;
    background-position: center;
    text-align:center ;
    padding: 40px 0;
    color: #fff;
    margin: 200px,auto,0;
    box-shadow: 0,10px,10px rgba(0,0,0,0.2);


}
.stopwatch h1 {
    margin-top: 60px;


}
.buttons{
    display: flex;
    align-items: center;
    justify-content: center;
}
.buttons img{
    width: 50px;
    margin: 0 20px;
    cursor: pointer;

}
.buttons img:nth-child(2){
width: 80px;

}                        

        </div>
    </body>
</html>

