
# inputTags

`inputTags` es un plugin de jQuery que permite agregar, editar y eliminar etiquetas en campos de entrada. Ofrece opciones de autocompletado, validación y personalización de eventos, brindando una experiencia de usuario enriquecida para el manejo de etiquetas.

## Características
- Autocompletado para sugerir etiquetas.
- Validación de etiquetas con opciones de longitud mínima y máxima.
- Limita la cantidad de etiquetas permitidas.
- Admite múltiples teclas de activación para añadir etiquetas.
- Control sobre eventos como creación, actualización y eliminación de etiquetas.

## Instalación
Incluye jQuery (2.1.4 o superior) y el archivo `inputTags.js` en tu proyecto:
```html
<script src="https://code.jquery.com/jquery-2.1.4.min.js"></script>
<script src="ruta/a/inputTags.js"></script>
```

## Uso Básico
Inicializa `inputTags` en el elemento de entrada:
```javascript
$('#miInput').inputTags({
    tags: ['ejemplo1', 'ejemplo2'],
    minLength: 3,
    maxLength: 20,
    max: 5,
    autocomplete: {
        values: ['sugerencia1', 'sugerencia2'],
        only: true
    }
});
```

## Opciones
Las opciones personalizables de `inputTags` incluyen:

- **tags**: `[Array]` Lista inicial de etiquetas para mostrar.
- **inputKeys**: `[Array]` Define teclas específicas para confirmar la inserción de una etiqueta mientras se escribe. **Default**: ',', Enter. 
- **minLength**: `[Number]` Longitud mínima de una etiqueta (por defecto: `2`).
- **maxLength**: `[Number]` Longitud máxima de una etiqueta (por defecto: `30`).
- **max**: `[Number]` Número máximo de etiquetas permitidas (por defecto: `6`).
- **email**: `[Boolean]` Exige que las etiquetas tengan formato de email.
- **only**: `[Boolean]` Impide duplicación de etiquetas.
- **editable**: `[Boolean]` Permite que las etiquetas existentes se puedan editar.
- **insertOnBlur**: `[Boolean]` Inserta la etiqueta al perder el foco en el campo de entrada.

### Opciones de Autocompletado
Controla las sugerencias de autocompletado:

- **autocomplete.values**: `[Array]` Lista de valores para autocompletado.
- **autocomplete.only**: `[Boolean]` Si es `true`, solo permite seleccionar valores de autocompletado.

### Opciones de Errores
Personaliza los mensajes de error que aparecen al validar las etiquetas:

- **errors.empty**: Mensaje para etiquetas vacías.
- **errors.minLength**: Mensaje si la etiqueta es demasiado corta.
- **errors.maxLength**: Mensaje si la etiqueta es demasiado larga.
- **errors.max**: Mensaje si se alcanza el número máximo de etiquetas.
- **errors.email**: Mensaje si la etiqueta no tiene formato de email.
- **errors.exists**: Mensaje si la etiqueta ya existe.
- **errors.autocomplete_only**: Mensaje cuando se requiere usar autocompletado.
- **errors.timeout**: Tiempo en milisegundos para mostrar el mensaje de error (por defecto: `8000`).

### Eventos
Define funciones para ciertos eventos:

- **init**: Al inicializar el plugin.
- **create**: Al crear una etiqueta.
- **update**: Al actualizar una etiqueta.
- **destroy**: Al eliminar una etiqueta.
- **focus**: Al enfocar el campo de entrada.
- **selected**: Al seleccionar una etiqueta.
- **unselected**: Al deseleccionar una etiqueta.
- **change**: Al cambiar el valor del campo.
- **autocompleteTagSelect**: Al seleccionar una etiqueta desde la lista de autocompletado.

## Ejemplo Completo
```javascript
$('#miInput').inputTags({
    tags: ['etiqueta1', 'etiqueta2'],
    inputKeys: [',', ';', ' '],
    minLength: 3,
    maxLength: 20,
    max: 5,
    email: false,
    only: true,
    insertOnBlur: true,
    autocomplete: {
        values: ['JavaScript', 'Python', 'Ruby'],
        only: true
    },
    errors: {
        empty: 'No se puede agregar una etiqueta vacía.',
        minLength: 'La etiqueta debe tener al menos %s caracteres.',
        maxLength: 'La etiqueta no debe exceder %s caracteres.',
        max: 'Solo se permiten %s etiquetas.',
        email: 'La etiqueta no tiene formato de email válido.',
        exists: 'Esta etiqueta ya existe.',
        autocomplete_only: 'Seleccione una etiqueta de la lista.',
        timeout: 5000
    }
});
```