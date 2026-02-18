# Diseño de Arquitectura del Sistema

## 1. Objetivo
Documentar la estructura general del sistema y cómo se integran los componentes de consulta de datos (REST y GraphQL) para asegurar una comunicación eficiente entre el cliente y el servidor de datos,,.

## 2. Diagrama de Componentes (Mermaid)
A continuación, se presenta la representación visual de la arquitectura del proyecto:

```mermaid
graph TD
    subgraph Cliente
        App[Aplicación de Usuario]
    end

    subgraph Capa_de_Servicios
        REST[API REST - PokéAPI]
        GQL[API GraphQL - Pokemon Playground]
    end

    subgraph Gestion_de_Datos
        JSON[Respuesta JSON Masiva]
        Optimized[Respuesta JSON Eficiente]
    end

    App -- "Petición GET (Over-fetching)" --> REST
    REST -- "Retorna Todo el Recurso" --> JSON
    App -- "Consulta Específica (Query)" --> GQL
    GQL -- "Retorna Solo Datos Requeridos" --> Optimized