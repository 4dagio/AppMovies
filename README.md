# Central médica - IG-SW1


## Objetivo:
 Una compañía desea construir una aplicación que soporte un centro de llamadas de enfermeras, respondiendo preguntas de clientes (pacientes) acerca de potenciales problema de salud. 
 
## Propuesta de arquitectura

![IG-Propuesta drawio (1)](https://user-images.githubusercontent.com/3275936/183535813-23e18d47-a5d4-450e-a3d5-8b00e7933322.png)


## Diseño de la solución

## Decisiones

- Se propone construir la solución implementando los servicios ofrecidos por **Azure** para satisfacer adecuadamente a los atributos:
-- **Alta disponibilidad:** (Atender a los diferentes usuarios del sistema con la prioridad requerida).
-- **Elasticidad y Escalabilidad:** (Preparar la solución para nuevos canales de atención).
-- **Resiliencia:** (Recuperación ante desastres)
-- **Seguridad:** (Mantener la integridad y privacidad de la información clínica sensible)


## Descripción de componentes


- [Front Door] - Con el fin de garantizar el rendimiento y disponibilidad de los canales para las engfermeras/usuarios
- [WAF] - Para garantizar protección contra DDoS, Bots
- [B2C] - Azure B2C administrará la autenticación y autorización de los usuarios (Configurar el APi connector para expandir la funcionalidad y conectar a la central de usuarios)
- [APIM] - Como puerta de acceso a los dominios de pacientes y protección de recursos
- [Dominio de pacientes] - Servicios expuestos para administrar las historias clínicas **CosmosDB** y remisiones de pacientes a través del hub de notificaciones.
- [Bot Service] - Dominio cognitivo para apoyar a las enfermeras y usuarios en el diagnóstico correcto.
