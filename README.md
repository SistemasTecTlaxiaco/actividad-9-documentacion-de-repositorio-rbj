LogiTech – Plataforma Descentralizada de Préstamos EstudiantilesDescripción del ProyectoLogiTech es una solución de financiamiento educativo basada en Web3 que conecta a estudiantes con fondos de apoyo de manera directa y transparente. A diferencia de los sistemas bancarios tradicionales, LogiTech utiliza contratos inteligentes para gestionar la asignación de recursos, asegurando que el capital llegue a quienes cumplen con los requisitos académicos, sin burocracia excesiva.El sistema utiliza la red Stellar (Soroban) para garantizar que cada préstamo otorgado sea inmutable y rastreable, permitiendo una auditoría pública del flujo de los fondos destinados a la educación.Características PrincipalesGestión de Solicitudes: Los estudiantes pueden subir sus perfiles y necesidades de financiamiento directamente a la plataforma.Smart Contracts (Soroban): Automatización de la aprobación y desembolso de fondos mediante lógica programada en Rust.Transparencia Total: Registro público de los préstamos otorgados para evitar el desvío de recursos.Arquitectura de Microservicios: Backend robusto desarrollado en Java 25 para manejar la lógica de negocio y usuarios a gran escala.Seguridad Criptográfica: Integración con wallets digitales para la recepción y pago de cuotas.Objetivos del ProyectoObjetivo GeneralImplementar una plataforma descentralizada que facilite el acceso a préstamos estudiantiles mediante tecnología blockchain, eliminando intermediarios financieros y reduciendo costos operativos.Objetivos EspecíficosDesarrollar un Smart Contract en Soroban para la administración del fondo común de préstamos.Construir una API Gateway y microservicios en Spring Boot para la gestión de usuarios y expedientes.Integrar firmas digitales para asegurar la validez de los contratos de préstamo.Validar el flujo de transacciones en la Stellar Testnet.Arquitectura del SistemaEl proyecto se divide en una estructura híbrida para maximizar el rendimiento y la descentralización:PlaintextLogiTech/
│
├── logitech-contract/   → Smart Contract (Rust + Soroban)
├── logitech-api/        → Microservicios Backend (Java 25 + Spring Boot)
└── logitech-docs/       → Documentación técnica y diagramas
Flujo de la AplicaciónFragmento de códigograph TD
    A[Estudiante sube solicitud] --> B[Validación en Microservicio]
    B --> C{Cumple Requisitos?}
    C -- Sí --> D[Contrato Inteligente genera Préstamo]
    C -- No --> E[Notificación de Rechazo]
    D --> F[Envío de Fondos a Wallet Estudiante]
    F --> G[Registro Inmutable en Stellar]
    G --> H[Seguimiento de Pagos en Tiempo Real]
Tecnologías UtilizadasSmart Contracts: Rust & Soroban (Stellar Network).Backend: Java 25, Spring Boot 3.x (Estructura de Controladores, Modelos y Repositorios).Base de Datos: PostgreSQL (para datos no críticos) y Blockchain (para datos financieros).Herramientas: Cargo, Maven, Docker, Soroban CLI.Instalación y Configuración1. Clonar el repositorioBashgit clone https://github.com/TuUsuario/LogiTech.git
cd LogiTech
2. Compilar y Desplegar el Contrato (Soroban)Bashcd logitech-contract
cargo build --target wasm32-unknown-unknown --release
soroban contract deploy --wasm target/wasm32-unknown-unknown/release/logitech.wasm --source admin --network testnet
Guarda el Contract ID generado para configurar el backend.3. Configurar el Backend (Spring Boot)Asegúrate de tener instalado el JDK 25. Configura tu archivo application.properties:Propertiesstellar.contract.id=TU_CONTRACT_ID
stellar.network=testnet
server.port=8080
4. Ejecutar la AplicaciónBash./mvnw spring-boot:run
Endpoints Principales (API REST)MétodoEndpointDescripciónPOST/api/prestamos/solicitarRegistra una nueva solicitud de préstamo.GET/api/prestamos/historial/{id}Consulta el estado del préstamo en la blockchain.POST/api/pagos/abonarEjecuta un pago hacia el Smart Contract.ConclusiónLogiTech no es solo una herramienta financiera, es un ecosistema que empodera al estudiante y asegura que el capital de apoyo educativo se maneje con la máxima integridad tecnológica posible.
