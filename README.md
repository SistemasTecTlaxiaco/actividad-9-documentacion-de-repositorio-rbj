# LogiTech – Plataforma Descentralizada de Préstamos Estudiantiles

## Descripción del Proyecto
**LogiTech** es una solución de financiamiento educativo basada en **Web3** que conecta a estudiantes con fondos de apoyo de manera directa y transparente. A diferencia de los sistemas bancarios tradicionales, LogiTech utiliza contratos inteligentes para gestionar la asignación de recursos, asegurando que el capital llegue a quienes cumplen con los requisitos académicos.

El sistema utiliza la red **Stellar (Soroban)** para garantizar que cada préstamo otorgado sea inmutable y rastreable, permitiendo una auditoría pública del flujo de los fondos destinados a la educación.

---

## Características Principales
* **Smart Contracts (Soroban):** Automatización de la aprobación y desembolso de fondos mediante lógica programada en Rust.
* **Transparencia Total:** Registro público de los préstamos otorgados para evitar el desvío de recursos.
* **Arquitectura de Microservicios:** Backend robusto desarrollado en Java 25 para manejar la lógica de negocio.
* **Seguridad Criptográfica:** Integración con wallets digitales para la recepción y pago de cuotas.

---

## Objetivos del Proyecto

### Objetivo General
Implementar una plataforma descentralizada que facilite el acceso a préstamos estudiantiles mediante tecnología blockchain, eliminando intermediarios financieros.

### Objetivos Específicos
* Desarrollar un **Smart Contract** en Soroban para la administración del fondo común de préstamos.
* Construir una **API Gateway** y microservicios en Spring Boot para la gestión de usuarios.
* Validar el flujo de transacciones en la **Stellar Testnet**.

---

## Arquitectura del Proyecto

```text
LogiTech/
│
├── logitech-contract/   → Smart Contract (Rust + Soroban)
├── logitech-api/        → Microservicios Backend (Java 25 + Spring Boot)
└── logitech-docs/       → Documentación técnica
Flujo de la AplicaciónRegistro: El estudiante sube su solicitud.Validación: El microservicio en Java verifica los requisitos.Aprobación: El Smart Contract genera el préstamo automáticamente.Desembolso: Envío de fondos a la wallet del estudiante.Trazabilidad: Registro inmutable en la red Stellar.Instalación y Configuración1. Clonar el repositorioBashgit clone [https://github.com/SistemasTecTlaxiaco/actividad-9-documentacion-de-repositorio-rbj.git](https://github.com/SistemasTecTlaxiaco/actividad-9-documentacion-de-repositorio-rbj.git)
2. Compilar Contrato (Soroban)Bashcd logitech-contract
cargo build --target wasm32-unknown-unknown --release
3. Ejecutar API (Spring Boot)Bashcd logitech-api
./mvnw spring-boot:run
Endpoints Principales (API REST)MétodoEndpointDescripciónPOST/api/prestamos/solicitarRegistra una nueva solicitud.GET/api/prestamos/historial/{id}Consulta el estado en blockchain.POST/api/pagos/abonarEjecuta un pago al contrato.ConclusiónLogiTech empodera al estudiante y asegura que el capital educativo se maneje con la máxima integridad tecnológica, eliminando la corrupción y los retrasos burocráticos.
### ¿Cómo pegarlo para que no falle?
1. **Borra todo** lo que está en el cuadro negro de tu captura.
2. Copia el texto de arriba (desde el primer `#` hasta el final).
3. Pégalo.
4. Dale clic a la pestaña que dice **"Preview"** (arriba del cuadro de texto). Si lo ves con títulos grandes y tablas, ¡ya quedó!
5. Dale al botón verde de **"Commit changes"**.

¡Avísame si en el "Preview" ya se ve bien ordenado!
