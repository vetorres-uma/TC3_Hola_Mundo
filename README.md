# 👋 Hola Mundo (TwinCAT 3)

## 📝 Descripción del Proyecto

Este proyecto es el **Hola Mundo** de la programación de **autómatas programables (PLC)**. 

El proyecto **Hola Mundo** se ha desarrollado en el entorno **TwinCAT 3** empleando el lenguaje **Texto Estructurado (ST)** conforme a la norma **IEC 61131-3**.

Hola Mundo es un proyecto mínimo y funcional, que muestra la declaración y el uso básico de variables booleanas y enteras, ubicadas en los espacios de memoria de marcas, imagen de entrada e imagen de salida. Cubriendo los elementos esenciales de programación del lenguaje ST de la norma **IEC 61131-3** para la programación de PLC.

![Imagen](./assets/V_Hola_Mundo.png){width=430px}

Este proyecto incluye además, una **visualización** elemental que permite, mediante objetos gráficos, interactuar con las variables del proyecto. Utilizando **formas rectangulares**, para mostrar el valor de variables booleanas y numéricas, y **botones**, para modificar el valor de variables booleanas y numéricas.

---

### Estructura (simplificada) del Proyecto PLC (POUs):

```text
TC3_Hola_Mundo/
├── TC3_Hola_Mundo.sln             <-- Solución de Visual Studio
└── TC3_Hola_Mundo/                <-- Proyecto TwinCAT
    └── Hola_Mundo_PLC/            <-- Proyecto PLC
        ├── POUs/
        │   └── MAIN.TcPOU         <-- Programa principal (Código ST)
        └── VISUs/
            └── V_Hola_Mundo.TcVISU <-- Interfaz gráfica (Visualización)
            
```
--- 

## Código

!!! info "Parte de Declaración"
    ```iecst
    // Hola Mundo de la Programación de PLCPROGRAM MAIN
    VAR
        ContadorCiclos: UINT;
        i_Pulsador AT %I*: BOOL;
        o_Lampara  AT %Q*: BOOL;
    END_VAR
    ```

!!! info "Parte de Implementación"
    ```iecst
    ContadorCiclos := ContadorCiclos + 1;
    o_Lampara := i_Pulsador;
    ```

---

## Comentarios

- La interfaz del programa `MAIN` (cabecera y definición de variables) se define en la **Parte de Declaración**. 
- Los **comentarios** de una línea empiezan con `//`.
- La variable `ContadorCiclos` se declara como un entero sin signo (`UINT`).
- La variable `i_Pulsador` se declara como un **booleano** (`BOOL`) y se localiza dinámicamente en la **Imagen de Entrada** (`AT %I*`).
- La variable `o_Lampara` se declara como un **booleano** (`BOOL`) y se localiza dinámicamente en la **Imagen de Salida** (`AT %Q*`).
- La variable `ContadorCiclos` se incrementa indefinidamente una vez por **Ciclo Básico** de ejecución del PLC (10 ms).
- El código del módulo, en lenguaje ST, se incluyue en la **Parte de Implementación**.
- La variable de salida `o_Lampara` copia, continuamente, el valor de la variable de entrada `i_Pulsador`.
- El valor de la variable `ContadorCiclos` se muestra en rectángulo gris la visualización.
- El valor de la variable `ContadorCiclos` se se puede cambiar escribiéndolo en rectángulo blanco la visualización.
- La variable `ContadorCiclos` puede reiniciarse accionando el pulsador `Reinicia`.
- El valor de la variable `o_Lampara` se muestra con el cambio de color del rectángulo `Lampara` (verde claro = `FALSE`, verde oscuro = `TRUE`).
- El valor de la variable `i_Pulsador` cambia cuando se acciona el botón `Pulsador`.

---

## 💻 Requisitos del Sistema

### Software

- **IDE:** Microsoft Visual Studio / TwinCAT 3 XAE (Versión mínima recomendada: **3.1.4024.x**).
- **Lenguajes:** Texto Estructurado (ST).
- **Target System:** Controlador Beckhoff, runtime local o UmRT_Default

---

## 🚀 Puesta en Marcha

Para descargar, compilar y ejecutar este proyecto en el entorno de TwinCAT 3, siga los siguientes pasos:

1. **Clonar Repositorio:**

```bash
    git clone https://github.com/vetorres-uma/TC3_Hola_Mundo.git
```

2. **Abrir el Proyecto:** abra el archivo `.sln` (Solución) ubicado en la carpeta principal utilizando el entorno de ingeniería **TwinCAT XAE** (integrado en Visual Studio).
1. **Selección del Controlador:** seleccione el simulador (**UmRT_Default**) o controlador local o remoto (**Choose Runtime System**).
1. **Activación de Configuración:** en el modo **Configuración**, active la configuración (**Activate Configuration**) y reinicie TwinCAT en modo Ejecución (**Run Mode**).
1. **Carga del Código:** en el entorno PLC, inicie la sesión y descargue el programa al PLC (**Login**).
1. **Poner el código en ejecución:** ejecute la lógica de control en el controlador **Start** (F5). Puede utilizar la visualización integrada en el proyecto PLC para facilitar la prueba.

---

## 🤝 Contribuciones

Este proyecto se utiliza con fines educativos y de prueba. Las contribuciones, sugerencias o correcciones de errores son bienvenidas. Por favor, abra un Issue o envíe un Pull Request si deseas contribuir.

---

## 🧑‍💻 Autor

- **Autor Principal:** Victor Torres [@vetorres-uma](<https://github.com/vetorres-uma>)
- **Revisor**: Francisco Ángel Moreno [@famoreno](<https://github.com/famoreno>)
- **Revisor**: Manuel Castellano [@mcastellanoquero](<https://github.com/mcastellanoquero>)

---

## ⚖️ Licencia

Este proyecto es de código abierto y está disponible bajo la **Licencia Pública General GNU (GPL)**.

- Consulte el archivo `LICENSE` para más detalles.
  