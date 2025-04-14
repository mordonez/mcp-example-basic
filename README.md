# MCP Weather API

Un servidor MCP (Model Context Protocol) simple que proporciona información meteorológica utilizando la API del Servicio Meteorológico Nacional de EE.UU. (NWS).

Este proyecto ha sido desarrollado siguiendo el tutorial oficial de la documentación de MCP: [https://modelcontextprotocol.io/quickstart/server#node](https://modelcontextprotocol.io/quickstart/server#node)

## Características

- Obtener alertas meteorológicas activas para cualquier estado de EE.UU.
- Obtener pronósticos meteorológicos para cualquier ubicación en EE.UU. usando coordenadas de latitud/longitud

## Requisitos

- Node.js (versión 16 o superior)
- NPM (incluido con Node.js)

## Instalación

1. Clona este repositorio:
   ```bash
   git clone https://github.com/mordonez/mcp-example-basic.git
   cd mcp-example-basic
   ```

2. Instala las dependencias:
   ```bash
   npm install
   ```

3. Compila el proyecto:
   ```bash
   npm run build
   ```

## Uso con Claude Desktop

1. Añade la configuración del servidor MCP al archivo de configuración de Claude en:
   `~/Library/Application Support/Claude/claude_desktop_config.json`

   ```json
   {
     "mcpServers": {
       "weather": {
         "command": "node",
         "args": [
            // Ejemplo: /Users/mordonez/Development/GitHub/mcp-example-basic/build/index.js
           "/ruta/completa/a/mcp-example-basic/build/index.js"
         ]
       }
     }
   }
   ```

2. Reinicia la aplicación Claude Desktop

3. Ahora puedes pedir a Claude que use las herramientas meteorológicas:
   - "Muéstrame las alertas meteorológicas activas para Texas"
   - "Que tiempo hace en Nueva York?"

## Herramientas disponibles

### `get-alerts`
Obtiene alertas meteorológicas activas para un estado de EE.UU.

**Parámetros:**
- `state`: Código de estado de dos letras (p.ej., CA, NY)

### `get-forecast`
Obtiene el pronóstico meteorológico para una ubicación.

**Parámetros:**
- `latitude`: Latitud de la ubicación (entre -90 y 90)
- `longitude`: Longitud de la ubicación (entre -180 y 180)

## Desarrollo

- El código fuente está en TypeScript en el directorio `src/`
- El código compilado se genera en el directorio `build/`

Para recompilar después de cambios:
```bash
npm run build
```

## Licencia

ISC
