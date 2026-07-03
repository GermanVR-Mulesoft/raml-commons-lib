# RAML Commons Library (RAML 1.0)

## Descripción General
Este repositorio contiene la librería centralizada para el desarrollo de APIs (`raml-commons-lib`), diseñada para estandarizar y unificar las especificaciones RESTful en toda la organización. Proporciona un conjunto reutilizable de fragmentos RAML 1.0 que garantizan la consistencia arquitectónica, reducen la duplicación de código y aceleran el ciclo de vida del desarrollo.

## Estructura del Repositorio
La arquitectura de la librería está organizada modularmente para facilitar su consumo y mantenimiento, exponiendo sus recursos a través del archivo principal `library.raml`:

```
├── exchange.json
├── LICENSE
├── library.raml
├── README.md
├── resourceTypes
│   ├── collection.raml
│   ├── health-check.raml
│   └── item.raml
├── securitySchemes
│   ├── client-id-enforcement.raml
│   └── oauth2.raml
├── traits
│   ├── errors
│   │   └── standard-errors.raml
│   ├── headers
│   │   └── correlation-id.raml
│   ├── query
│   │   ├── pagination.raml
│   │   └── sorting.raml
│   ├── requests
│   │   ├── request-binary.raml
│   │   ├── request-json.raml
│   │   ├── request-multipart.raml
│   │   └── request-xml.raml
│   └── responses
│       ├── response-200-file.raml
│       ├── response-200-json.raml
│       ├── response-200-xml.raml
│       ├── response-201-json.raml
│       ├── response-202-json.raml
│       └── response-204-empty.raml
└── types
    ├── ErrorResponse.raml
    ├── health
    │   ├── Dependency.raml
    │   └── HealthResponse.raml
    └── PaginatedResponse.raml
```

## Capacidades y Fragmentos Disponibles

*   **Resource Types:** Implementa patrones estándar de diseño para colecciones (`collection.raml`) y elementos individuales (`item.raml`).
*   **Security Schemes:** Centraliza las políticas de acceso y autenticación corporativas, soportando tanto `client-id-enforcement` como `oauth2`.
*   **Gestión de Errores y Cabeceras:** Estandariza las respuestas de error a través de `standard-errors.raml` y exige trazabilidad mediante la cabecera `correlation-id.raml`.
*   **Parámetros de Consulta (Query):** Proporciona comportamientos reutilizables para operaciones de lectura complejas mediante `pagination.raml` y `sorting.raml`.
*   **Contratos de Petición y Respuesta (Traits):** 
    *   **Requests:** Soporta validación de entradas para múltiples formatos incluyendo JSON, XML, Multipart y datos binarios.
    *   **Responses:** Estandariza las salidas basándose en códigos de estado HTTP (200, 201, 202, 204) garantizando las mejores prácticas RESTful.
*   **Tipos de Datos Base:** Define estructuras de datos transversales que deben ser utilizadas en todas las APIs, tales como `ErrorResponse.raml` y `PaginatedResponse.raml`.

## Despliegue y Publicación
Este repositorio está preparado para ser publicado como un Fragmento RAML (Asset) en Anypoint Exchange. El archivo `exchange.json` contiene la configuración necesaria para la correcta indexación de la librería. 

Cualquier API dentro de la organización debe importar esta librería como dependencia en Design Center o Anypoint Studio antes de definir tipos de datos o endpoints locales.