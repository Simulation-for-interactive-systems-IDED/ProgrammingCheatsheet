# Repaso rápido de C#

Aquí encontraras un repaso rápido de C#, sintaxis básica del lenguaje y ejemplos de uso.

## 1. Crear clase

La `clase` es un "molde/plano de construcción" que nos permitirá instanciar (crear) objetos.
```
class MyCoolClass {

}
```
## 2. Instanciar objeto
Para instanciar un objeto usamos el keyword `new`. El resultado es un nuevo objeto,
```
new MyCoolClass();
```
## 3. Variables
Podemos "almacenar la referencia" del nuevo objeto en una variable.
```
MyCoolClass nombreDeVariable; // Se crea una variable que almacenara objetos del tipo MyCoolClass
nombreDeVariable = new MyCoolClass(); // Instanciamos un nuevo objeto y asignamos su referencia a la variable
```
Lo anterior se puede hacer en una linea.
```
MyCoolClass nombreDeVariable = new MyCoolClass();
```

## 3. Declarando y definiendo métodos
Se puede indicar que métodos tendrá un objeto, declarando métodos en la clase.
```
class MyCoolClass {
	// Un método que no devolverá nada (void), no recibirá nada y es publicamente accesible desde afuera del objeto.
	public void DoSomething() {
		// Here you write some code...
	}
}
```
## 4. Invocando métodos de un objeto
```
MyCoolClass nombreDeVariable = new MyCoolClass(); // Crea un nuevo objeto
nombreDeVariable.DoSomething(); // Invoca el método DoSomething del objeto
```

## 3. Declarando y definiendo métodos que devuelven y reciben cosas
```
class MyCoolClass {
	// Un método que no devolverá nada (void), no recibirá nada y es publicamente accesible desde afuera del objeto.
	public void DoSomething() {
		// Here you write some code...
	}
	
	// Un método que no devolverá nada (void), recibirá un int y es publicamente accesible desde afuera del objeto.
	public void DoSomethingWithInput(int someNum) {
		// Here you write some code...
	}
	
	// Un método que devolverá un int, recibirá un int y es publicamente accesible desde afuera del objeto.
	public int IncrementNumber(int someNum) {
		return someNum + 1; // Incrementa el numero que recibe y devuelve el resultado.
	}
}
```
## 5. Invocando más métodos de un objeto
```
MyCoolClass nombreDeVariable = new MyCoolClass(); // Crea un nuevo objeto

// Invoca el método DoSomething del objeto
nombreDeVariable.DoSomething(); 

// Invoca el método DoSomethingWithInput del objeto
nombreDeVariable.DoSomethingWithInput(5);

// Invoca el método IncrementNumber del objeto y almacena el resultado devuelto en una variable (¿Qué valor almacenará la variable numIncremented?)
int numIncremented = nombreDeVariable.IncrementNumber(5); 
```

## 6. Instanciando más objetos
Es posible crear muchos objetos a partir de una única clase.
```
MyCoolClass firstObject = new MyCoolClass();
MyCoolClass secondObject = new MyCoolClass();
MyCoolClass thirdObject = new MyCoolClass();
MyCoolClass fourthObject = new MyCoolClass();
MyCoolClass fifthObject = new MyCoolClass();
// ... Continue instancing objects
```

## 7. Variables de un objeto (fields/campos)
Cada objeto que instancio tiene definida una cantidad de variables, estas son independientes entre cada objeto. Para indicar que un objeto tendrá "variables" o "fields" debo declararlas en la clase que se usa para instanciar el objeto.
```
class MyVector2D {
	public float x;
	public float y;
}
```
Ejemplo:
```
MyVector2D firstVector = new MyVector2D();
firstVector.x = 1;
firstVector.y = 2;

MyVector2D secondVector = new MyVector2D();
secondVector.x = 3;
secondVector.y = 4;
```
Cada uno de los objetos instanciados tendrá su propia "versión" de las variables `x` y `y`, que es independiente para cada objeto.

## 8. Constructor de una clase
Cada vez que instancio un objeto se invoca una "función" especial conocida como el constructor, en este podremos entre otras cosas inicializar variables del objeto, invocar métodos, etc. La idea del constructor es escribir código que nos permita "construir" o "inicializar" el estado de los nuevos objetos que creamos.
```
class MyVector2D {
	float x;
	float y;
	
	// Un constructor que no recibe nada
	public MyVector2D() {
		// Codigo aqui
	}
}
```

A continuación un constructor que recibe dos números.
```
class MyVector2D {
	float x;
	float y;
	
	// Un constructor que no recibe nada
	public MyVector2D(float firstComponent, float secondComponent) {
		// Las variables 'x' y 'y' de los objetos será inicializada con lo que reciba el constructor
		x = firstComponent;
		x = secondComponent;
	}
}
```
Ahora con el constructor podemos reescribir:
```
MyVector2D firstVector = new MyVector2D();
firstVector.x = 1;
firstVector.y = 2;

MyVector2D secondVector = new MyVector2D();
secondVector.x = 3;
secondVector.y = 4;
```
En lo siguiente:
```
MyVector2D firstVector = new MyVector2D(1, 2);
MyVector2D secondVector = new MyVector2D(3, 4);
```
## 9. Más ejemplos con métodos
```
class MyVector2D {
	float x;
	float y;
	
	// Un método que recibe otro objeto del tipo MyVector2D y devuelve un nuevo objeto del tipo MyVector2D 
	public MyVector2D Add(MyVector2D otherVectorObject) {
		return new MyVector2D(x + otherVectorObject.x, y + otherVectorObject.y);
	}

	// Un método que recibe un número y devuelve un nuevo objeto del tipo MyVector2D 
	public MyVector2D Scale(float scaleFactor) {
		return new MyVector2D(x * scaleFactor, y * scaleFactor);
	}

	// Un método que no recibe nada y devuelve otro objeto del tipo MyVector2D
	public MyVector2D Clone() {
		return new MyVector2D(x, y);
	}

	// Un método que no recibe nada y no devuelve nada (pero dibuja un vector en la pantalla)
	public void Draw() {
		Debug.DrawLine(new UnityEngine.Vector2(0, 0), new UnityEngine.Vector2(x, y));
	}
}
```

# External links

- [Introducción interactiva a C# by Microsoft](https://docs.microsoft.com/es-es/dotnet/csharp/tour-of-csharp/tutorials/) **<-- recommended**
- [C# Tutorial by TutorialsPoint](https://www.tutorialspoint.com/csharp/index.htm)
- [C# Tutorial by JavatPoint](https://www.javatpoint.com/c-sharp-tutorial)