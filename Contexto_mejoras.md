# Auditoría y evolución de Luis Portfolio mediante AIDLC

## 1. Rol y objetivo
Actúa como un **Senior Frontend Engineer**, **UI/UX Designer** y **Software Architect**, con experiencia en diseño de portafolios profesionales para desarrolladores de software, perfiles técnicos senior y futuros arquitectos de software.

Tu objetivo es realizar una auditoría integral del proyecto **Luis Portfolio** y, a partir de los hallazgos, proponer e implementar mejoras que eleven su calidad visual, experiencia de usuario, estructura, contenido y mantenibilidad.

No quiero un simple cambio de colores ni una plantilla genérica de portafolio. Quiero que evalúes críticamente la solución actual y determines cómo puede evolucionar para comunicar mejor mi identidad profesional, diferenciarme de otros desarrolladores y proyectar una imagen sólida, moderna y coherente con mis objetivos profesionales.

Utiliza el enfoque **AIDLC (AI-Driven Development Life Cycle)** para organizar el análisis, las decisiones, la implementación y la validación. No ejecutes cambios sin comprender primero la arquitectura y el estado actual del proyecto.

---

## 2. Contexto del proyecto
**Luis Portfolio** es mi página personal y portafolio profesional.

La intención es presentar mi perfil como profesional de tecnología, destacando mi experiencia en desarrollo backend, cloud, liderazgo técnico, diseño de soluciones y evolución hacia la arquitectura de software.

La página debe servir como carta de presentación profesional para oportunidades laborales, contactos técnicos y personas interesadas en conocer mi experiencia y mis proyectos.

### Identidad profesional que debe transmitir
- **Profesionalismo y criterio técnico.**
- **Capacidad para desarrollar soluciones de software mantenibles.**
- **Experiencia en backend, cloud e integración de sistemas.**
- **Evolución de desarrollador hacia líder técnico y arquitecto de software.**
- **Capacidad para analizar problemas, tomar decisiones técnicas y comunicar ideas complejas.**
- **Interés por construir soluciones útiles sin caer en complejidad innecesaria.**
- **Identidad personal auténtica**, sin aparentar experiencias, conocimientos o responsabilidades que no pueda respaldar.

> La página no debe parecer un portafolio de principiante ni una plantilla genérica generada por IA. Debe transmitir una identidad profesional propia, con decisiones visuales intencionales y contenido bien organizado.

---

## 3. Restricciones y principios no negociables

### 3.1. Arquitectura frontend-first
La solución debe seguir siendo una aplicación principalmente frontend.

**Prioriza:**
- Generación estática de páginas cuando sea compatible con la solución actual.
- HTML semántico, CSS y JavaScript/TypeScript del lado del cliente cuando sea necesario.
- Aprovechamiento de las capacidades existentes del framework.
- Contenido estático o archivos de configuración para proyectos, experiencia, habilidades y demás información.
- Despliegue sencillo en un servicio de hosting estático o una plataforma compatible con el proyecto actual.

No introduzcas un backend propio, una API, una base de datos, un sistema de autenticación ni servicios de infraestructura adicionales sin una necesidad real y justificada.

**Evita incorporar:**
- Servidores dedicados para renderizar páginas que pueden generarse estáticamente.
- Bases de datos para información que puede mantenerse en archivos locales.
- CMS, microservicios o arquitecturas distribuidas innecesarias.
- Dependencias de servicios externos para funcionalidades que pueden resolverse de forma sencilla en frontend.
- Sistemas de analítica, seguimiento o recopilación de datos que no sean necesarios.
- Librerías pesadas para resolver interacciones simples.
- Automatizaciones de despliegue o procesos operativos complejos que no aporten un beneficio claro.

*Si propones una funcionalidad que requiera un servicio externo, explica por qué es necesaria, su coste potencial, sus implicaciones de mantenimiento y si existe una alternativa sin backend.*

### 3.2. Principio de simplicidad
La solución debe ser fácil de desarrollar, mantener, probar y desplegar.

**Aplica estos principios:**
- No sobreingenierizar.
- No introducir abstracciones sin una necesidad concreta.
- No reconstruir funcionalidades que ya funcionan correctamente.
- No cambiar el framework o la arquitectura base solo por preferencias personales.
- No añadir dependencias sin evaluar su valor.
- No sacrificar rendimiento o accesibilidad en favor de efectos visuales.
- No ampliar el alcance con funcionalidades ajenas al objetivo del portafolio.

*Toda mejora debe tener una razón clara y un beneficio identificable.*

### 3.3. Respeto por el proyecto existente
- Antes de modificar código, inspecciona el repositorio y comprende su estado real.
- Conserva las funcionalidades, el contenido válido, la identidad existente y las decisiones técnicas que sigan siendo adecuadas.
- No elimines secciones, recursos, configuraciones o dependencias sin comprobar primero su propósito.
- No inventes información profesional, experiencia, métricas, certificaciones, clientes ni resultados. Si falta información necesaria, identifica el dato como pendiente y utiliza contenido provisional únicamente cuando sea seguro y claramente identificable.

---

## 7. Restricciones de contenido y privacidad
El portafolio es una página pública.

- No publiques secretos, credenciales, tokens, variables de entorno, información personal innecesaria, datos confidenciales de clientes ni detalles internos de sistemas corporativos.
- No copies información privada desde otros repositorios o archivos locales sin verificar que sea apropiada para una publicación pública.
- Conserva los enlaces profesionales existentes que sean válidos y evita inventar enlaces a perfiles, repositorios o proyectos.

---

## 8. Criterios de aceptación
Consideraremos satisfactoria la evolución del proyecto si:

1. La página comunica con claridad quién soy y qué valor profesional aporto.
2. El diseño se percibe coherente, moderno, distintivo y profesional.
3. La experiencia y los proyectos son fáciles de explorar.
4. La jerarquía visual y la legibilidad mejoran.
5. La experiencia móvil funciona correctamente.
6. Se mantienen o mejoran la accesibilidad y el rendimiento.
7. La estructura del código sigue siendo comprensible y mantenible.
8. No se introduce un backend propio ni infraestructura innecesaria.
9. El proyecto conserva un despliegue sencillo.
10. La compilación y las comprobaciones disponibles terminan satisfactoriamente.
11. No se inventa información profesional ni se expone información confidencial.
12. Las decisiones de diseño y arquitectura pueden justificarse por su aporte al objetivo del portafolio.

---

## 9. Instrucción final
Empieza inspeccionando el repositorio y entendiendo el estado actual del proyecto.

Después realiza el diagnóstico, define las mejoras prioritarias e implementa los cambios que estén justificados dentro de las restricciones indicadas.

No reconstruyas todo desde cero por defecto. No agregues funcionalidades solo para que el proyecto parezca más sofisticado. No conviertas un portafolio estático en una aplicación compleja.

El objetivo no es tener más código, más animaciones ni más tecnologías. El objetivo es conseguir un portafolio profesional notablemente mejor, con una identidad visual sólida, una experiencia de usuario cuidada, una estructura mantenible y un despliegue simple.

Trabaja con autonomía dentro de ese alcance, valida los cambios y entrega el resultado funcional junto con un resumen concreto de lo que mejoraste y por qué.