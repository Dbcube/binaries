# Dbcube Binaries

Este repositorio contiene los binarios precompilados de los motores de base de datos de Dbcube.

## 📦 Binarios Disponibles

Dbcube utiliza tres motores principales:

- **Query Engine** (`query-engine`): Motor de consultas SQL para MySQL, PostgreSQL y SQLite
- **Schema Engine** (`schema-engine`): Motor de gestión de esquemas y migraciones
- **SQLite Engine** (`sqlite-engine`): Motor especializado para operaciones SQLite

## 🖥️ Plataformas Soportadas

Cada binario está disponible para las siguientes plataformas:

| Plataforma | Arquitectura | Nomenclatura |
|------------|--------------|--------------|
| Windows | x64 | `windows-x64` |
| Windows | ARM64 | `windows-arm64` |
| Linux | x64 | `linux-x64` |
| Linux | ARM64 | `linux-arm64` |
| macOS | x64 | `macos-x64` |
| macOS | ARM64 (M1/M2) | `macos-arm64` |

## 📥 Descarga Automática

Los binarios se descargan automáticamente cuando usas Dbcube en tu proyecto. No necesitas descargarlos manualmente.

### Ubicaciones de Instalación

Los binarios se instalan automáticamente en una de las siguientes ubicaciones (en orden de prioridad):

1. **`.dbcube/bin/`** - En la raíz de tu proyecto
2. **`node_modules/.dbcube/bin/`** - Dentro de node_modules
3. **`<temp>/.dbcube/bin/`** - Directorio temporal del sistema (fallback)

## 🔧 Instalación Manual

Si necesitas instalar manualmente los binarios, puedes usar el CLI de Dbcube:

### Instalar todos los binarios (latest)

```bash
npm install -g @dbcube/cli
dbcube run download
```

### Instalar un binario específico

```bash
# Query Engine
dbcube run download query-engine

# Schema Engine
dbcube run download schema-engine

# SQLite Engine
dbcube run download sqlite-engine
```

### Instalar una versión específica

```bash
dbcube run download query-engine v3.2.1
dbcube run download schema-engine v3.1.0
dbcube run download sqlite-engine latest
```

## 📋 Estructura de Releases

Cada release contiene archivos ZIP con la siguiente estructura:

```
query-engine-latest-windows-x64.zip
├── query-engine-windows-x64.exe

schema-engine-latest-linux-arm64.zip
├── schema-engine-linux-arm64

sqlite-engine-latest-macos-x64.zip
├── sqlite-engine-macos-x64
```

## 🔗 URLs de Descarga

Los binarios se descargan desde GitHub Releases:

```
https://github.com/Dbcube/binaries/releases/download/{engine-type}/{engine}-{version}-{platform}-{arch}.zip
```

**Ejemplos:**
```
https://github.com/Dbcube/binaries/releases/download/query-engine/query-engine-latest-windows-x64.zip
https://github.com/Dbcube/binaries/releases/download/schema-engine/schema-engine-v3.2.1-linux-x64.zip
https://github.com/Dbcube/binaries/releases/download/sqlite-engine/sqlite-engine-latest-macos-arm64.zip
```

## ⚙️ Uso Programático

### Desde Node.js/TypeScript

```typescript
import { Binary } from '@dbcube/core';

// Los binarios se descargan automáticamente al primer uso
const binaries = await Binary.get();

console.log(binaries.query_engine);  // Ruta al query engine
console.log(binaries.schema_engine); // Ruta al schema engine
```

### Verificar Instalación

```bash
# Listar binarios instalados
ls .dbcube/bin/

# En Windows
dir .dbcube\bin\
```

## 🔄 Actualización de Binarios

### Actualizar todos los binarios a latest

```bash
dbcube run upgrade
```

Este comando:
1. Elimina todos los binarios anteriores
2. Descarga las últimas versiones
3. Instala los nuevos binarios

### Verificar versiones instaladas

Revisa el archivo [`versions.json`](./versions.json) para ver todas las versiones disponibles.

## 🛠️ Construcción de Binarios

Los binarios son compilados desde Rust con las siguientes optimizaciones:

```bash
# Query Engine
cd query-engine
cargo build --release

# Schema Engine
cd schema-engine
cargo build --release

# SQLite Engine
cd sqlite-engine
cargo build --release
```

Los binarios optimizados se encuentran en `target/release/`.

## 📄 Licencia

MIT License - Ver [LICENSE](./LICENSE) para más detalles.

## 🐛 Reportar Problemas

Si encuentras algún problema con los binarios:

1. Verifica que tu plataforma esté soportada
2. Intenta ejecutar `dbcube run upgrade` para actualizar
3. Reporta el problema en [GitHub Issues](https://github.com/Dbcube/binaries/issues)

## 🔐 Verificación de Integridad

Todos los binarios son:
- ✅ Compilados desde fuentes verificadas
- ✅ Firmados digitalmente (cuando sea posible)
- ✅ Escaneados para detectar malware
- ✅ Distribuidos a través de GitHub Releases oficial

## 📊 Estadísticas de Descarga

Puedes ver las estadísticas de descarga de cada release en la [página de Releases](https://github.com/Dbcube/binaries/releases).

---

**Desarrollado por [Albert Araya](https://github.com/albrtaraya)** • [Documentación](https://github.com/Dbcube/query-builder) • [NPM](https://www.npmjs.com/org/dbcube)
