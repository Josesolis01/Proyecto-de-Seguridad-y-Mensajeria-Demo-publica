# Proyecto de Seguridad y Mensajería — Demo pública

- **Resumen**: Repositorio con implementaciones y ejemplos para estudiar seguridad en comunicaciones y mensajería. Contiene servicios de autenticación, mensajería, gestión de sesiones, utilidades criptográficas y ejemplos de clientes/servidores (con y sin TLS). Diseñado como demostración técnica y para uso en entornos de laboratorio.

**Estructura del repositorio**
- `source-code/`: Código fuente (servicios, clientes, utilidades y certificados de prueba).
- `pruebas-logs/`: Capturas de red (`.pcapng`) y registros de pruebas y ejecución.

**Componentes destacados**
- `auth_service.py`: Servicio de autenticación y control de acceso.
- `messaging_service.py`: Lógica de mensajería entre clientes.
- `session_service.py`: Gestión de sesiones y menú interactivo por socket.
- `serversocket.py` / `clientsocket.py`: Ejemplos básicos de servidor/cliente por sockets.
- `generar_certificados.py`: Genera certificados de prueba para sesiones TLS.
- `db_crypt.py` / `descifrar.py`: Utilidades de cifrado/descifrado aplicadas a la base de datos.
- `mitm.py`, `replay.py`, `clientsocket_atack.py`: Scripts de diagnóstico/ataque con fines educativos — usarlos solo en entornos controlados y con autorización.

**Requisitos**
- Python 3.8 o superior.
- Dependencias de terceros (lista en `requirements.txt`):
	- `bcrypt` — hashing de contraseñas.
	- `cryptography` — generación/gestión de certificados y operaciones criptográficas.
	- `psycopg2-binary` — adaptador PostgreSQL (si usas PostgreSQL).

**Instalación (Windows, PowerShell)**
1. Abrir PowerShell en la carpeta del proyecto:

```powershell
cd C:\Users\yosis\Desktop\PAI2-main\PAI2-main
```

2. Crear y activar un entorno virtual (recomendado):

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
```

3. Instalar dependencias desde `requirements.txt`:

```powershell
pip install -r requirements.txt
```

Notas para Windows:
- Si `psycopg2-binary` da problemas, instala las "Build Tools" o usa la rueda precompilada para Windows.
- Para `cryptography` en Windows es preferible instalar la versión binaria; normalmente `pip` lo resolverá.

**Uso rápido**
- Generar certificados de prueba (opcional):

```powershell
python .\source-code\generar_certificados.py
```

- Iniciar servidor TLS de ejemplo:

```powershell
python .\source-code\server_prueba.py
```

- Iniciar servidor NO-TLS (modo inseguro de pruebas):

```powershell
python .\source-code\server_warning.py
```

- Ejecutar cliente de ejemplo (inseguro o TLS según el script):

```powershell
python .\source-code\clientsocket.py
```

Revisa los comentarios al inicio de cada script en `source-code/` para parámetros adicionales.

**Pruebas y registros**
- `pruebas-logs/captura_INSEGURO.pcapng` y `pruebas-logs/captura_TLS1.3.pcapng`: capturas de red para análisis.
- `pruebas-logs/*.txt`: logs y ficheros de ejemplo (login, mensajes, transacciones).

**Seguridad y uso responsable**
- Los certificados incluidos y las credenciales en ejemplos son solo para pruebas; no usar en producción.
- No publiques credenciales reales ni datos personales en el repositorio.
- Las herramientas de ataque/diagnóstico (`mitm.py`, `replay.py`, `clientsocket_atack.py`) son para uso educativo y deben ejecutarse únicamente en entornos controlados y autorizados.

**Contribuciones**
- Para mejoras: abre un `issue` o un `pull request` con una descripción clara de los cambios.

**Licencia y contacto**
- No se incluye `LICENSE` por defecto. Recomiendo añadir una licencia (por ejemplo, MIT) antes de publicar.
- Si quieres, añado una sección con tu nombre y contacto.

---

