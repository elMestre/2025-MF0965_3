# Examen

## Instrucciones

### Crea un entorno virtual

```bash
python -m venv nombre_proyecto
```

### Activación entorno virtual

```bash
nombre_proyecto\Scripts\activate
```

### Instalar requerimientos

```bash
pip install -r .\requirements.txt
```

### Cambia la configuración de la base de datos

Revisa el fichero `config.py` y excribe tus datos de configuración

## Enunciado

#### Requisitos generales (Git)

- Mantener la **separación en capas** (UI, Service, Persistence).
- Cada cambio significativo debe ir en un **commit** aparte con mensaje descriptivo. **Cabe la posibiliodad de hacer más commits de los indicados**
- Prueba las operaciones de inserción y actualización en la base de datos real.
- Documenta brevemente en el README cómo ejecutar la aplicación y las dependencias necesarias.

#### Listado de países

*Tiempo estimado 20 minutos*

- Adaptar la capa de persistencia y la lógica de negocio para consultar la tabla `country`.

- La consulta SQL deberá devolver estos campos:

  1. `country.Code`
  2. `country.Name`
  3. `country.Population`

- Mostrar esos resultados en el `Treeview` de la UI.

> **Commit #1:** “Adapta la consulta a world.country de países”.

#### Capitales

*Tiempo estimado 20 minutos*

- Adaptar la capa de persistencia y la lógica de negocio para consultar la tabla `country` junto con la tabla `city` (capital).

- La consulta SQL deberá devolver estos campos:

  1. `country.Code`
  2. `country.Name`
  3. `country.Population`
  4. `city`.`Name` como Capital
  5. `city`.`POPULATION` como Población Capital

- Mostrar esos resultados en el `Treeview` de la UI.

> **Commit #2:** “Mostrar Pais y Capital”.

---

#### Panel de Alta / Edición de Países

*Tiempo estimado 30 minutos*

- Crear una nueva ventana (o diálogo) que sirva para **añadir** o **editar** un país.
- En esta ventana se deberán ver todos los campos del País

> **Commit #2:** “Crear panel de alta/edición de país”.

---

#### Conexión de botones “Añadir” / “Editar”

*Tiempo estimado 20 minutos*

- Modificar los botones de la UI principal para que:
  - Al pulsar **Añadir**, abra el formulario en modo “nuevo país”.
  - Al pulsar **Editar**, abra el mismo formulario rellenado con los datos del país seleccionado.
  - El panel de país tendrá un botón de `Guardar` con un callback que se le pasará como parámetro al instanciarse

> **Commit #4:** “Conectar botones Añadir/Editar al panel de país”.

#### Acción de “Añadir” / “Editar”

*Tiempo estimado 20 minutos*

- Definir un **callback** que se ejecute al pulsar “Guardar” y que invoque al `CountryService` para:
  - Insertar un nuevo registro en `country`
  - O actualizar los datos de un país existente
- Tras guardar los cambios, el `Treeview` deberá refrescarse automáticamente para reflejar la inserción o la actualización.

> **Commit #5:** “Guardar Añade/Editar los paises. Se refresca el listado”.

---
