# imc
calculadora de indice de massa corporal

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <link rel="stylesheet" href="https://unpkg.com/purecss@2.1.0/build/pure-min.css" integrity="sha384-yHIFVG6ClnONEA5yB5DJXfW2/KC173DIQrYoZMEtBvGzmf0PKiGyNEqe9N6BNDBH" crossorigin="anonymous">
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>calculo IMC</title>
    <style>
        body{
            margin-left: 20%;
            margin-right: 20%;
           
        }
    </style>
</head>
<body>
    <form name="formImc" class="pure-form pure-form-form-stacked"
        <fieldset>

        <legend>IMC</legend>

        <label for="Inome">nome:</label>
        <input type="text" name="nome" id="Inome" placeholder="digite seu nome:"><br><br>

        <label for="Ipeso">peso:</label>
        <input type="number" name="peso" id="Ipeso" placeholder="digite seu peso:"><br><br>

        <label for="Ialtura">altura:</label>
        <input type="number" name="altura" id="Ialtura" placeholder="digite seu altura:"><br><br>

        <input type="button" value="calcular" onclick="calc()" class="pure-button pure-button-primary">
        </fieldset>
    </form>
        <h2 id="resultado"></h2>


        <script>
            function calc(){
                var peso, nome, altura, imc, status;
                

                nome= formImc.nome.value;
                peso= formImc.peso.value;
                altura= formImc.altura.value;

                peso= parseFloat(peso)
                altura= parseFloat(altura)

                imc= peso/(altura*altura);
                console.log(imc);
                
                var result = document.getElementById("resultado");
                console.log(result)

            if(imc<=18.5){
                var status = " abaixo do peso ";
                document.getElementById("resultado").style.color = "blue"
            }
            else if(imc>=18.6 && imc<=24.9){
                var  status = " parabéns, você está no peso ideal";
                document.getElementById("resultado").style.color = "purple";
            }
            else if(imc>25.0 && imc<=29.9){
                var status = " você está levemente acima do peso ";
                document.getElementById("resultado").style.color = "red";
            }
            else if(imc>=30.0 && imc<=34.9){
                var status = " você está com obesidade de grau 1 ";
                document.getElementById("resultado").style.color = "gray";
            }
            
            else if(imc>=35.0 && imc<=39.9){
                var status = " você está com obesidade de grau 2 ";
                document.getElementById("resultado").style.color = "Navy blue";
            }
            else{
                var status = " você está com obesidade grau 3 ";
                document.getElementById("resultado").style.color = "pink";
            }
                result.textContent = " o seu indice de massa corporal é "  + imc.toFixed(2) + status;
            }

        </script>
</body>
</html>
