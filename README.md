
# BugTracker - ABM Usuarios


## 1. Clonar Repositorio (Clone/Checkout)

**1.1. Ejecutar comando clone para descargar repositorio:** 
```sh
$ git clone https://github.com/utn-frc-pav1-3k5-2020/actividad_abm_usuarios.git
```
**1.2. Ubicarse en la carpeta generada con el nombre del repositorio: 

```sh
$ cd actividad_abm_usuarios
```

**1.3. Crear un nuevo branch (rama)**

Para crear una nueva rama (branch) y saltar a ella, en un solo paso, puedes utilizar el comando  `git checkout`  con la opción  `-b`, indicando el nombre del nuevo branch (reemplazando el nro de legajo) de la siguiente forma branch_{legajo}, para el legajo 12345:

```sh
$ git checkout -b branch_12345 
Switched to a new branch "12345"
```
Y para que se vea reflejada en GitHub:
```sh
$ git push --set-upstream origin branch_12345
```

## 2. Temas
> Iniciar la solución que se encuentra en la carpeta src/BugTracker.sln
Se agregaron 2 formularios. 
> - frmUsuario: Consulta los usuarios registrados con un filtro por "Nombre" y Perfil (que se elige de un combo)
> - frmABMUsuario: Permite hacer el Alta y Modificación de usuarios, que previamente se seleccionaron en frmUsuario.

**2.1. Enum (Enumeraciones)**

La palabra clave enum se utiliza para declarar una enumeración, un tipo distinto que consiste en un conjunto de constantes con nombre denominado lista de enumeradores.
Normalmente suele ser recomendable definir una enumeración directamente dentro de un espacio de nombres para que todas las clases de dicho espacio puedan tener acceso a esta con la misma facilidad. Sin embargo, una enumeración también puede anidarse dentro de una clase o estructura.
De manera predeterminada, el primer enumerador tiene el valor 0 y el valor de cada enumerador sucesivo se incrementa en 1. Por ejemplo:

```csharp
	enum TipoDocumento
	{
		DNI, // 0
		NIE, // 1
		Pasaporte, // 2
		Otro = 99
	};
```
**2.2. INSERT**

Ejemplo:
```sql
	INSERT [Usuarios] ([id_usuario], [id_perfil], [usuario], [password], [email], [estado]) 
	VALUES (1, 1, 'ADMIN', '123', 'admin@bt.com', 'S')
```

**2.3. UPDATE**

Ejemplo:

```sql
	UPDATE Usuarios
       SET usuario = ADMIN,
           password = 123, 
           email = admin@bt.com, 
           id_perfil = 1
     WHERE id_usuario = 1
```


## 3. Actividad

Sobre el formulario `frmABMUsuario` realizar las siguientes actividades:

**3.1. Validar Campos Obligatorios.**
En el método ValidarCampos agregar las validaciones que faltan sobre los textbox:
* txtPassword
* txtConfirmarPass
* cboPerfil

**3.2. Actualizar Usuario.**
Implementar lógica en BusinessLayer y DataAccessLayer para actualizar los datos de un usuario.

**3.3. Eliminado lógico de Usuario.**
El borrado lógico consiste en utilizar una columna de la tabla de Usuarios (borrado: true/false) como una marca que indica si fue eliminado o no un elemento. 



## 4. Versionar en GitHub los cambios locales (add / commit / push)

> A continuación vamos a crear el **commit** y subir los cambios al servidor GitHub.

4.1. **Status**. Verificamos los cambios pendientes de versionar.

```sh
$ git status
```

4.2. **Add**. Agregamos todos los archivos nuevos no versionados.

```sh
$ git add -A
```

4.3. **Commit**. Generamos un commit con todos los cambios y agregamos un comentario.

```sh
$ git commit -a -m "Comentario"
```

4.4. **Push**. Enviamos todos los commits locales a GitHub

```sh
$ git push
```

4.5. **Status**. Verificar que no quedaron cambios pendientes de versionar

```sh
$ git status
```
