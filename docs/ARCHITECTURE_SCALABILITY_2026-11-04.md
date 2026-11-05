# flask-portfolio-architecture-study — Plan técnico y escalabilidad viable

**Corte:** 2026-11-04. **Naturaleza:** análisis técnico y propuesta gradual, no auditoría de despliegue ni compromiso comercial.

## Evidencia de partida

Proyecto Flask con capas DTO/repository/templates y código migrado desde una referencia a Daniel117622.

## Arquitectura y límites de complejidad

Conservar loaders y patrón Repository desacoplado, distinguir mocks de Mongo real, agregar tests cliente Flask y adaptadores tipados. En despliegue usar servidor WSGI y reverse proxy, no servidor de desarrollo Flask.

## Observabilidad y crecimiento

Medir tiempo de render, consultas por página, cache aplicable, tamaño de plantillas y memoria. Crecer de hosting simple a instancias replicadas solo si sesiones/storage son externos y hay demanda medible.

## Condiciones para avanzar

Revisar atribución/licencia del origen, no usar templates_original privados, prohibir secretos en git y documentar procedencia en NOTICE.

### Evidencia obligatoria

Registrar commit, fecha, rama, comandos ejecutados, resultado y limitaciones. Conservar autoría, licencias, contenido sensible y aprobaciones de terceros. Configurar rollback y backup **antes** de publicación; no suponer que CI valida apariencia o legalidad.

### Bibliografía técnica (consultada 2026-11-04)

[Flask deployment with Gunicorn](https://flask.palletsprojects.com/en/stable/deploying/gunicorn/) · [NIST SSDF](https://csrc.nist.gov/pubs/sp/800/218/final).

Las fuentes constituyen buenas prácticas generales: métricas, seguridad, cumplimiento y resultados deben verificarse en cada repositorio.
