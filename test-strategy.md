1. (Linea 49) esta mal, ya que al no poner punto, no llama a ninguna clase.

- Anterior: const lowOrHi = document.querySelector('lowOrHi');
- Correccion: const lowOrHi = document.querySelector('.lowOrHi');


1. La constante ATTEMPS solo tiene 5 intentos (linea 46)

    - Se corrigio a 10 intentos
        - const ATTEMPS = 10;


3. La variable randomNumber contiene un numero aleatorio con un rango de 0 a 10 (linea 44) y (linea 125)
    - Anterior: let randomNumber = Math.random() * 10;

    - Por lo que se modifico para que el numero aleatorio tenga un rango de 1 a 100
        Correccion: let randomNumber = Math.floor(Math.random() * 100) + 1;
    - Se agreogo Math.floor ya que sirve para redondear si se genera un numero decimal y se suma 1 para que el numero 
    empiece desde 1 y no desde 0



4.  Hay un error de tipografia en la (linea 98), la palabra 'Event' debe de empezar con mayuscula,
    De igual manera dentro de la funcion setGameOver() (linea 106)

- Anterior:  guessSubmit.addeventListener('click', checkGuess); 
- Correccion: guessSubmit.addEventListener('click', checkGuess); 


5. En la (linea 57) sobre la  funcion checkGuess()
    - Se tiene que realizar la conversion de la entrada del usuario a integer, para que la entrada se
    pueda comparar con el numero aleatorio y que solo se ingresen numeros enteros y no decimales.
        - Anterior: let userGuess = guessField.value;
        - Correccion: let userGuess = parseInt(guessField.value);


6. (linea 66) sobre la funcion checkGuess() mala
    - La condicional para evaluar si el usuario perdio, esta mal 'if (userGuess === randomNumber)', 
    ya que se debe de evaluar si el contador es igual a los intentos permitidos 'if (guessCount === ATTEMPS)'


7. (linea 72) sobre la funcion checkGuess() mala
    - La condicional para evaluar si el usuario gano el juego, esta mal  'if (guessCount === ATTEMPS)',
    ya que se debe de evaluar si el usuario adivino el numero 'if (userGuess === randomNumber)'


8.  Se debe de agregar una condicional dentro de la funcion checkGuess() para poder evaluar que el numero ingresado esta en el rango de 1 a 100

- Si la condicion es valida se realizaran las condicionales que evaluan si el numero es correcto o incorrecto, agregado en la (linea 59)
    - if(userGuess >= 1 && userGuess <= 100)


- Si la condicion no se cumple, mostrara una alerta indicando que el numero ingresado esta fuera de rango, restandole 1 al contador,
para que no se incremente un intento, agregado en la (linea 89)
    - alert('Debe de ingresar un numero entero que este en el rango entre 1 y 100');
      guessCount = guessCount - 1;


9. Se debe de agregar en la (linea 75) la siguiente correcion para vaciar la etiqueta p.lowOrHi al momento que sea adivinado el numero

    - Correccion: lowOrHi.textContent = '';


10. Por ultimo se corrigio el color de las clases lastResult en la funcion checkGuess() (linea 68, 74 y 80)

- En donde el fondo de la etiqueta p.lastResult cambia de color verde al encontrar el numero aleatorio, en color negro si el 
numero registrado es incorrecto y color rojo si fallo en todos los intentos 

