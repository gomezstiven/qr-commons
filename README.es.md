# QR Commons

[English](./README.md) · **Español**

Herramientas open-source, local-first y de alta confiabilidad para generar códigos QR estáticos que realmente te pertenecen.

> Los códigos QR estáticos son una utilidad, no una suscripción.

QR Commons busca convertir la generación de QR estáticos en una primitiva pública confiable: sin cuentas obligatorias, redirecciones propietarias, tracking del contenido, enlaces que expiran ni dependencia de infraestructura controlada por QR Commons.

No intentamos diferenciarnos porque podamos “crear un QR”. Existen miles de generadores. El valor del proyecto está en ofrecer una base **correcta, determinista, portable, auditable, privada por arquitectura y práctica para integrar**.

## Estado del proyecto

**Pre-alpha / diseño R0.1.** El repositorio ya tiene un boundary de proyecto aceptado y está definiendo el primer milestone ejecutable portable.

R0.1 establece la infraestructura OSS y los contratos mínimos para un core determinista de QR estáticos antes de construir una experiencia web completa.

Documentos principales —actualmente canónicos en inglés—:

- [R0.1 — Portable Static Core](./docs/milestones/R0.1.md)
- [R0.1 Infrastructure](./docs/architecture/R0.1-INFRASTRUCTURE.md)
- [Public Infrastructure Quality Model](./docs/architecture/PUBLIC-INFRASTRUCTURE.md)
- [Language Policy](./docs/LANGUAGE-POLICY.md)

## Qué queremos construir

QR Commons debe poder ser usado de forma confiable por:

- una persona desde la futura herramienta web gratuita;
- una empresa integrándolo en sus propios sistemas;
- una institución pública que necesite revisar y auditar el código;
- una imprenta o flujo de producción que genere grandes volúmenes;
- un developer desde librerías o automatizaciones;
- un equipo que prefiera self-hosting;
- un producto downstream que no quiera depender de nuestros servidores.

Un QR estático exportado debe seguir funcionando aunque QR Commons desaparezca mañana, siempre que el destino codificado siga existiendo.

## Principios

1. **Estático significa estático.** El contenido codificado corresponde directamente al payload seleccionado por el usuario.
2. **Local-first.** Generar un QR estático no debería requerir enviar su contenido a un servidor.
3. **Sin lock-in.** Los artefactos exportados deben seguir siendo útiles sin QR Commons.
4. **Corrección antes que decoración.** Legibilidad, estructura, quiet zones y confiabilidad tienen prioridad sobre styling.
5. **Determinismo.** Una misma entrada canónica debe producir una salida canónica reproducible dentro de una versión determinada.
6. **Dependencias mínimas y justificadas.** Cada dependencia de runtime aumenta la superficie de confianza y debe ganarse su lugar.
7. **Generación no es resolución.** Redirects dinámicos, analytics y gestión de destinos pertenecen a otra capa.
8. **La usabilidad también es infraestructura.** APIs claras, defaults razonables, errores útiles y documentación forman parte de la calidad del proyecto.

## Primer pipeline

R0.1 busca establecer la referencia mínima:

```text
text payload
    ↓
@qr-commons/core
    ↓
QR Commons symbol / borderless matrix
    ↓
@qr-commons/renderer
    ↓
deterministic SVG
    ↓
independent conformance
```

La matriz canónica no contiene el margen externo. El renderer es quien posee la quiet zone y la representación física.

## Capacidades previstas

Con el tiempo, el proyecto podrá incluir:

- URLs y texto plano;
- Wi-Fi, vCard, email, teléfono, SMS, ubicación y eventos;
- SVG determinista;
- PNG y formatos orientados a impresión;
- niveles explícitos de corrección de errores;
- logos con límites de seguridad verificables;
- styling de módulos y finders sujeto a conformance;
- validación de contraste y legibilidad;
- presets orientados a impresión;
- generación batch desde CSV/JSON;
- uso offline/PWA;
- paquetes reutilizables y CLI;
- herramientas de preflight para producción.

Estas capacidades entrarán progresivamente. R0.1 prioriza un core pequeño y verificable sobre una lista grande de features.

## Estructura del repositorio

```text
qr-commons/
├── apps/
│   └── web/                 # futura experiencia web de referencia
├── packages/
│   ├── core/                # modelo canónico y contrato de encoding
│   ├── formats/             # reservado hasta justificar API
│   ├── renderer/            # matrix → artifact; SVG primero
│   └── validator/           # reservado hasta justificar API pública
├── tests/
│   └── conformance/         # verificación independiente entre capas
├── docs/
│   ├── milestones/
│   ├── decisions/
│   └── architecture/
└── .github/
```

## Infraestructura pública

Nuestro objetivo de largo plazo puede resumirse así:

> Puedes auditarlo, ejecutarlo localmente, integrarlo, self-hostearlo, automatizarlo, exportar desde él y dejar de usarlo — sin que tus QR estáticos pasen a depender de nosotros.

Consulta el [Public Infrastructure Quality Model](./docs/architecture/PUBLIC-INFRASTRUCTURE.md) para la barra de calidad de reliability, portabilidad, privacidad, supply chain y conformance.

## Idiomas

El inglés es el idioma técnico canónico del código, APIs, ADRs y especificaciones normativas.

El español es el primer idioma de traducción oficial mantenida. Issues y discusiones pueden abrirse en inglés o español.

Consulta [LANGUAGE-POLICY.md](./docs/LANGUAGE-POLICY.md).

## Licencia

Apache License 2.0. Consulta [LICENSE](./LICENSE).

## Marca

Consulta [TRADEMARKS.md](./TRADEMARKS.md). “QR Code” es una marca registrada de DENSO WAVE INCORPORATED en Japón y otros países. QR Commons es un proyecto independiente y no está afiliado ni respaldado por DENSO WAVE.

## Autor

Creado por Stiven Gómez Barrientos como proyecto open-source independiente.
