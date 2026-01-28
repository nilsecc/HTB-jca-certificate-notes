
Make apps developed, deployed and mantained following the CIA principles (talking about the data the app manage).

`Develop --> Test --> Monitoring`

**`Security by Design` -->security isn't something you think about later, but rather you build into the app from the start**

When creating an app developers need to cover this: 
- `Threat modeling`: figure out potential risks to the app early on.
    
- `Secure code reviews`: After writing the code, developers carefully check it to make sure there are no weak spots
    
- `Servers and databases`: If they aren’t secure, the whole system is at risk.
    
- `Authentication and authorization`: Only the right people can get in, while authorization makes sure they can only access the data they’re allowed to.

### Responsability

```
CISO / Application Security Manager
       │
       ▼
Security Architects → Diseñan la estructura de seguridad
Developers → Escriben código seguro y aplican medidas de seguridad
IT Operations → Mantienen la seguridad en producción
```

```
Security Testers / Penetration Testers
- Análisis estático y dinámico
- Fuzzing y revisiones de código
- Simulación de ataques
- Evaluaciones continuas

```