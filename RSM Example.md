# Ejemplos de uso: Patrón RSM

Este documento contiene ejemplos prácticos de cómo implementar el patrón **RSM**, propuesto por Percy Alexander Caballero Lucano y patrocinado por BSG Perú.

Al Estructurar el proyecto puedes usar cualquier nombre para las carpetas, archivos o clases.

### Ejemplo de Estructura de Archivos
```
/
├── index.php
├── Routing/
│ └── Routing.php
├── Scheme/
│ └── Scheme.php
├── Manager/
│ └── Manager.php
├── Auxiliary/
│ └── Auxiliary.php
├── Broker/
│ └── Broker.php
├── Logs/
├── Assets/
└── ...
```

### Ejemplo de Codigo
```
index.php
    echo Routing::Accion('home');

Routing.php
    Class Routing
    {
        function Accion(valor)
        {
            return Scheme::Interfaz('home');
        }
    }

Scheme.php
    Class Scheme
    {
        function Interfaz(valor)
        {
            return Manager::Datos('home');
        }
    }

Manager.php
    Class Manager
    {
        function Datos(valor)
        {
            return Datos;
        }

        function DatosAux(valor)
        {
            return Auxiliary::Datos(valor);
        }

        function DatosBrk(valor)
        {
            return Broker::Datos(valor);
        }
    }

Auxiliary.php
    Class Auxiliary
    {
        function DatosAux(valor)
        {
            return Datos;
        }
    }

Broker.php
    Class Broker
    {
        function DatosBrk(valor)
        {
            return Datos;
        }
    }
```

### Notas
Estos ejemplos son simplificados para claridad.
En entornos reales, se puede integrar con sistemas de configuración externa, archivos .env, o incluso inyección de dependencias.

#### © 2025 Percy Alexander Caballero Lucano
#### Patrocinado por BSG Perú
