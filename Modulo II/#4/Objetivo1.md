# Objetivo 1: Estandarización de Vulnerabilidades (CVE y CWE)

## CVE- Common Vulnerabilities and Exposures

El término Vulnerabilidades y Exposiciones Comunes ( CVE, por sus siglas en inglés) generalmente se refiere a la lista CVE, es una base de datos de acceso público que identifica y cataloga las vulnerabilidades de seguridad conocidas en software y hardware. A cada vulnerabilidad se le asigna un identificador único, lo que facilita a las organizaciones compartir información, priorizar las soluciones y proteger sus sistemas.

## CWE - Common Weakness Enumeration

CWE (enumeración de debilidades comunes) es una lista estructurada de debilidades del software; considerado como un catálogo de fallas de codificación y diseño. Administrado por MITRACWE ayuda a identificar patrones que, si no se abordan, podrían provocar vulnerabilidades de seguridad.

## Diferencia entre CVE y CWE

El debate sobre CVE vs CWE surge a menudo porque ambos están estrechamente relacionados, pero tienen propósitos distintos. Mientras que CWE (Common Weakness Enumeration) cataloga posibles fallas en el diseño del código, CVE se centra en vulnerabilidades específicas identificadas en software del mundo real. Comprender Common Weakness Enumeration y Common Vulnerabilities and Exposures ayuda a cerrar la brecha entre el desarrollo y las operaciones, lo que garantiza que se implementen medidas de seguridad proactivas y reactivas.
<img width="746" height="459" alt="imagen" src="https://github.com/user-attachments/assets/4b762501-c103-4a1c-adcd-d31955165130" />

## Autoridades de Asignación (CNAs)

Los identificadores son asignados por las **CNAs (CVE Numbering Authorities)**, que son organizaciones autorizadas en todo el mundo (como grandes empresas tecnológicas, coordinadores de CERTs y centros de investigación) que descubren o reciben reportes de vulnerabilidades. La coordinación global es supervisada por MITRE.

## Fuentes de consulta

**CVE:** Se puede consultar en la base de datos oficial del MITRE (`cve.mitre.org`) o en el *National Vulnerability Database* (NVD) del NIST (`nvd.nist.gov`).

**CWE:** Se consulta directamente en el sitio oficial del proyecto CWE administrado por MITRE (`cwe.mitre.org`).

## Herramientas automatizadas

**OWASP Dependency-Check / Snyk:** Herramientas de análisis de composición de software (SCA) que escanean las dependencias y librerías de un proyecto para detectar si contienen CVEs conocidos.

**Nessus / OpenVAS:** Escáneres de vulnerabilidades de infraestructura y red que evalúan sistemas operativos y servicios activos contra bases de datos de CVEs.
