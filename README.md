# Calculator
![image](https://github.com/user-attachments/assets/e0c62571-bc05-4922-9372-4b1954e81173)

#HTML Code

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Calculator - by SamriddhFlex</title>
</head>

<body>
    <div class="calculator">
        <input type="text" placeholder="0" id="inputBox">
       <div>
        <button class="operator">AC</button>
        <button class="operator">DEL</button>
        <button class="operator">%</button>
        <button class="operator">/</button>
       </div>
    <div>
    <button>7</button>
    <button>8</button>
    <button>9</button>
    <button class="operator">*</button>
    </div>
    <div>
    <button>4</button>
    <button>5</button>
    <button>6</button>
    <button class="operator">-</button>
    </div>
    <div>
    <button>1</button>
    <button>2</button>
    <button>3</button>
    <button class="operator">+</button>
    </div>
    <div>
    <button>00</button>
    <button>0</button>
    <button>.</button>
    <button class="equalBtn">=</button>
    </div>
    </div>

    <script src="script.js"></script>


</body>

</html> 


#CSS CODE

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300&display=swap');
*{

    margin: 0;
    padding: 0;
    box-sizing : border-box;
    font-family: 'poppins', sans-serif;

}

body{
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(45deg,
    #0a0a0a, #3a4452);
}

.calculator{
    border: 1px solid #717377;
   
    padding: 14px;
    border-radius: 16px;
    background: transparent;
    box-shadow: 0px 3px 15px rgba(113, 115,
    119, 0.5);
    width: 363px;
}



input{
    width: 100%;
  
    padding: 24px;
    margin: 10px 1px ;
    background: transparent;
    box-shadow: 0px 3px 15px rgbs(84, 84, 84, 0.1);
    font-size: 40px;
    text-align: right;
    cursor: pointer;
    color: #ffffff;

}


input::placeholder{
    color:#ffffff;
}

button{
    border: none;
    width: 60px;
    height: 60px;
    margin: 10px;
    border-radius: 50%;
    background: transparent;
    color: #ffffff;
    font-size: 20px;
    box-shadow: -8px -8px 15px rgba(255, 255, 255, 0.1);
    cursor: pointer;
   
}

.equalBtn{
    background-color: #fb7c14;
}

.operator{
    color: #6dee0a;
}

#JavaScript CODE

let input = document.getElementById('inputBox');
// let buttons=document.getElementsByClassName('operator')
let buttons = document.querySelectorAll('button');

let string ="";
let arr = Array.from(buttons);
arr.forEach(buttons => {
    buttons.addEventListener('click',(e) =>{
        if(e.target.innerHTML == '='){
            string = eval(string);
            input.value = string;
        }

        // else if(e.target,innerHTML == 'AC'){
        //     string ="";
        //     input.value = string;
        // }
        else if(e.target.innerHTML=='AC'){
            string="";
            input.value=string;
        }
        else if(e.target.innerHTML == 'DEL'){
            string = string.substring(0, string.length-1);
            input.value = string;

        }
        else{
            string += e.target.innerHTML;
            input.value = string;
        }
    })

}) 
