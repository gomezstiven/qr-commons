# Contribuir a QR Commons

[English](./CONTRIBUTING.md) · **Español**

QR Commons está en etapa pre-alpha. Las contribuciones son bienvenidas, pero las decisiones de arquitectura y API pública deben mantenerse deliberadamente pequeñas hasta que el comportamiento del core esté probado.

El código, los identificadores, los commits y los artefactos técnicos normativos se mantienen en inglés. Sin embargo, puedes abrir issues y discutir propuestas en español o inglés.

## Principios para contribuir

- preservar la separación entre generación estática y resolución administrada;
- priorizar corrección, interoperabilidad y portabilidad sobre complejidad decorativa;
- no introducir cuentas, tracking, redirects o telemetría de payload como requisito para generación estática;
- mantener la lógica QR reutilizable fuera de la aplicación web de referencia;
- agregar o actualizar pruebas cuando cambie comportamiento;
- documentar nuevas dependencias y justificar por qué son necesarias;
- evitar ampliar APIs públicas antes de tener un caso de uso y conformance que las respalde;
- preferir cambios pequeños, revisables y reversibles.

## Flujo de trabajo

1. Selecciona o abre un issue para cambios no triviales.
2. Explica el problema y la capacidad mínima que quieres introducir.
3. Crea una rama enfocada.
4. Mantén los commits acotados y explica cambios de comportamiento.
5. Agrega o actualiza pruebas y fixtures.
6. Abre un pull request con scope, trade-offs, dependencias y validación realizada.

## Dependencias

Una dependencia de runtime forma parte de la superficie de confianza de QR Commons.

Una propuesta que agregue una dependencia debería explicar al menos:

- qué problema resuelve;
- por qué no conviene implementar esa capacidad directamente;
- licencia;
- dependencias transitivas;
- impacto en runtimes/bundle;
- cómo podría reemplazarse en el futuro detrás de un boundary propio.

## Idiomas

El inglés es el idioma técnico canónico del repositorio. El español es el primer idioma oficial de traducción.

Una contribución útil escrita en español no debe ser rechazada únicamente por no venir inicialmente traducida. El mantenedor puede añadir un resumen técnico en inglés cuando ayude a ampliar la revisión.

Consulta [docs/LANGUAGE-POLICY.md](./docs/LANGUAGE-POLICY.md).

## Gobernanza actual

QR Commons tiene actualmente un mantenedor principal. Las decisiones arquitectónicas duraderas se registran mediante ADRs y los cambios significativos se revisan públicamente mediante issues/PRs.

Consulta [GOVERNANCE.md](./GOVERNANCE.md).
