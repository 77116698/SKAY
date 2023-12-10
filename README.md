// Escribe una funcion que sume dos numeros eneros
function sumarEnteros(num1, num2) {
  if (Number.isInteger(num1) && Number.isInteger(num2)) {
    return num1 + num2;
  } else {
    return "Ambos argumentos deben ser números enteros.";
  }
}

// Ejemplo de uso
let resultado = sumarEnteros(5, 7);
console.log(resultado); // Salida esperada: 12

resultado = sumarEnteros(3, "Hola");
console.log(resultado); // Salida esperada: "Ambos argumentos deben ser números enteros."
// Escribe una funcion que se conecte a una api online y devuelva el resultado de la consulta en un array asociativo
async function consultarAPI(url) {
  try {
    const response = await fetch(url);

    if (!response.ok) {
      throw new Error(`Error en la solicitud: ${response.status}`);
    }

    const data = await response.json();
    return data;
  } catch (error) {
    console.error("Error al consultar la API:", error.message);
    return null;
  }
}

// Ejemplo de uso con una API de prueba (JSONPlaceholder)
const apiUrl = "https://jsonplaceholder.typicode.com/todos/1";
consultarAPI(apiUrl)
  .then(resultado => {
    console.log("Resultado de la consulta:", resultado);
  })
  .catch(error => {
    console.error("Error general:", error);
  });
  
