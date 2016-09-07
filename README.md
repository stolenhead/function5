# Lección 20 / Ejercicio 2

Closures / Hoisting

Requerimiento : El código muestra el mensaje JS coders love its callbacks, mientras que el resultado debería ser JS developers love its closures.

En el código inicial se puede observar que el resultado es: JS coders love its callbacks, esto sucede porque hay dos variables (una global y otra local) que tiene el mismo nombre, cuando el código comienze a ejecutarse el hoisting hará que la variable local sea elevada al inicio de su contexto pero solamente la declara mas no le da un valor (undefined) ,entonces cuando la condicional de flujo se ejecuta esta toma como verdadero la primera condición y nos retorna la primera sentencia (JS coders love its callbacks). La función prioriza el valor de la variable local que de la global, razón por la cual el retorno tomo el valor "callbacks".

var feature = 'closures'; 
(function () {     
    if ( typeof feature === 'undefined' ){         
        var feature = 'callbacks';         
        console.log('JS coders love its ' + feature );     
    } else {         
        console.log('JS developers love its ' + feature );     
    } 
})();
"JS coders love its callbacks"
Para la solución lo que realizo fue dejar a la variable global como unica variable y esta el tener un tipo de dato string la primara condición no se cumple, entonces se ejecuta la segunda sentencia. La funcion toma el valor de la varible global "Closures".
y se elmino el var en la funcion local.
var feature = 'closures'; 
(function () {     
    if ( typeof feature === 'undefined' ){
        feature = 'callbacks';
        console.log('JS coders love its ' + feature );     
    } else {         
        console.log('JS developers love its ' + feature );     
    } 
})();
"JS developers love its closures"
