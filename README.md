# LogiTech – Plataforma Descentralizada de Préstamos Estudiantiles

## 📝 Descripción del Proyecto
**LogiTech** es una solución de financiamiento educativo basada en tecnología **Web3**. Su objetivo es conectar a estudiantes con fondos de apoyo de manera directa, eliminando la burocracia de los bancos tradicionales.

Utilizando la red **Stellar (Soroban)**, el sistema garantiza que la asignación de recursos sea transparente, inmutable y verificable por cualquier ciudadano, asegurando que el apoyo llegue realmente a quienes cumplen con los requisitos académicos.

---

## 🚀 Características Principales
* **Descentralización:** No depende de una entidad bancaria central; la lógica reside en Smart Contracts.
* **Smart Contracts (Soroban):** Automatización total de la aprobación y desembolso de fondos mediante contratos desarrollados en Rust.
* **Backend de Alta Performance:** API construida con **Java 25** y **Spring Boot**, utilizando una arquitectura de microservicios.
* **Transparencia Inmutable:** Cada préstamo genera un hash único en la blockchain de Stellar para auditorías en tiempo real.
* **Seguridad:** Implementación de firmas digitales y manejo de claves privadas para transacciones seguras.

---

## 🎯 Objetivos del Proyecto

### Objetivo General
Desarrollar una plataforma integral de préstamos estudiantiles que utilice Blockchain para garantizar la integridad financiera y la eficiencia operativa en la entrega de apoyos educativos.

### Objetivos Específicos
* **Blockchain:** Implementar un contrato inteligente funcional en Soroban para la gestión de fondos.
* **Integración:** Conectar el ecosistema Java (Spring Boot) con la red Stellar mediante SDKs oficiales.
* **Escalabilidad:** Diseñar la base de datos (PostgreSQL) para coexistir con los datos on-chain.
* **Validación:** Desplegar en la Testnet de Stellar para pruebas de carga y seguridad.

---

## 🛠️ Tecnologías Utilizadas

| Componente | Tecnología |
| :--- | :--- |
| **Smart Contracts** | Rust + Soroban |
| **Backend** | Java 25 + Spring Boot 3.4 |
| **Blockchain** | Stellar Network (Testnet) |
| **Base de Datos** | PostgreSQL (Datos locales) |
| **Control de Versiones** | Git / GitHub |

---

## 📂 Arquitectura del Repositorio

```text
LogiTech/
│
├── logitech-contract/   → Código fuente del Smart Contract en Rust.
├── logitech-api/        → Microservicios en Java (Controller, Service, Repository).
├── logitech-docs/       → Diagramas de arquitectura y casos de uso.
└── README.md            → Documentación principal.
⚙️ Instalación y Uso
1. Requisitos Previos
Java 25 instalado.

Rust y Soroban CLI configurados.

Node.js (opcional para el frontend).

2. Clonar y Configurar
Bash
git clone [https://github.com/SistemasTecTlaxiaco/actividad-9-documentacion-de-repositorio-rbj.git](https://github.com/SistemasTecTlaxiaco/actividad-9-documentacion-de-repositorio-rbj.git)
cd actividad-9-documentacion-de-repositorio-rbj
3. Despliegue del Contrato
Bash
cd logitech-contract
cargo build --target wasm32-unknown-unknown --release
# Desplegar en Testnet
soroban contract deploy --wasm target/wasm32-unknown-unknown/release/logitech.wasm --source admin --network testnet
4. Iniciar Backend
Bash
cd ../logitech-api
./mvnw spring-boot:run
🔗 Endpoints de la API (Documentación)
POST /api/v1/solicitudes: Envía una nueva solicitud de préstamo al sistema.

GET /api/v1/blockchain/status/{hash}: Consulta el estado real de la transacción en Stellar.

POST /api/v1/pagos: Registra el abono de una cuota de préstamo mediante el Smart Contract.

🛡️ Seguridad y Buenas Prácticas
Variables de Entorno: Las claves privadas nunca se suben al repositorio (uso de .env).

Manejo de Errores: Implementación de GlobalExceptionHandler en el backend para flujos robustos.

Inmutabilidad: Los registros críticos no pueden ser modificados una vez confirmados en la blockchain.

🎓 Conclusión
LogiTech representa la evolución del financiamiento estudiantil, combinando la robustez de Java 25 con la transparencia de Web3. Es una herramienta diseñada para empoderar a los estudiantes y modernizar la gestión de recursos públicos y privados.
