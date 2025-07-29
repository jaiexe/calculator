HTML 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>calculator</title>
    <link rel="stylesheet" href="style.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Manrope:wght@200..800&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap" rel="stylesheet">
  
</head>
<body>
    <div class="calculator">
        <input type="text" placeholder="0" id="inputbox" readonly>
        <div>
            <form>
                <button class="operator" type="button">AC</button>
                <button class="operator" type="button">DEL</button>
                <button class="operator" type="button">%</button>
                <button class="operator" type="button">/</button>
            </form></div>
            <div>
            <form>
                <button type="button">7</button>
                <button type="button">8</button>
                <button type="button">9</button>
                <button class="operator"  type="button">*</button>
            </form>
            </div>
            <div>
            <form>
                <button  type="button">4</button>
                <button  type="button">5</button>
                <button  type="button">6</button>
                <button class="operator"  type="button">-</button>
            </form></div>
            <div>
            <form>
                <button  type="button">1</button>
                <button  type="button">2</button>
                <button  type="button">3</button>
                <button class="operator"  type="button">+</button>
            </form></div>
            <div>
            <form>
                <button  type="button">00</button>
                <button  type="button">0</button>
                <button  type="button">.</button>
                <button class="equalbtn"  type="button">=</button>
            </form></div>
        </div>
    </div>
    <script src="script.js" defer></script>
    
</body>
</html>

CSS
*{
    margin: 0;
    padding: 0;
    font-family: 'poppins',sans-serif;
    box-sizing: border-box;
}
body{
    background: linear-gradient(45deg,#0a0a0a,#3a4452);
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items:  center;
}
.calculator{
    
    
    border: 1px solid #717377;
    padding: 20px;
    border-radius: 16px;
    background:transparent;
    box-shadow: 0px 3px 15px rgba(113,115,119,0.5);


}
input{
    text-align: right;
    background: transparent;
    border: none;
    padding:24px;
    width: 320px;
    margin: 10px;
    box-shadow: 0px,3px,15px rgba(84,84,84,0.1);
    font-size: 40px;
    cursor: pointer;
    color: #ffffff;
}
input::placeholder{
    color: #ffffff;

}
button{
    border: none;
    width: 60px;
    height: 60px;
    margin: 10px;
    background: transparent;
    color: #ffffff;
    font-size: 20px;
    background-color: rgb(24, 23, 23);
    border-radius: 50%;
    box-shadow: -8px -8px 15px rgba(255,255,255,0.05);
    cursor: pointer;
}
.equalbtn{
    background-color: rgb(197, 78, 34);
}
.operator{
    color: rgb(142, 233, 5);
}
JAVASCRIPT

let input = document.getElementById("inputbox");
let buttons = document.querySelectorAll("button");
let string = "";

let arr = Array.from(buttons);
arr.forEach(button =>{
    button.addEventListener('click',(e) =>{
        if(e.target.innerHTML == '='){
            string=eval(string);
            input.value=string;
        }
        else if(e.target.innerHTML == 'AC'){
            string = "";
            input.value = string;
        }
        else if(e.target.innerHTML == 'DEL'){
            string = string.substring(0,string.length-1);
            input.value = string;
        }
        else{
            string += e.target.innerHTML;
            input.value = string;

        }
        
    });
});

    



