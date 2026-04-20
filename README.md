# 📦 Sistema de Pedidos - Patrones de Comportamiento

## 📌 Descripción

Este proyecto implementa un sistema backend para la gestión de pedidos utilizando **Spring Boot** y aplicando patrones de diseño de comportamiento:

* **Command**: Encapsula acciones sobre pedidos (confirmar, aplicar descuento) y permite deshacer operaciones.
* **Chain of Responsibility (CoR)**: Valida pedidos mediante una cadena de validadores (crédito, monto, stock).

El objetivo es lograr un sistema **desacoplado, extensible y fácil de mantener**.

---

## 🧩 Patrones implementados

### 🎯 Command

Permite ejecutar acciones como comandos independientes:

* `Comando` (interfaz)
* `ComandoAplicarDescuento`
* `ComandoConfirmar`
* `HistorialComandos` (soporta *undo*)

**Beneficios:**

* Desacopla quien solicita la acción de quien la ejecuta
* Permite deshacer operaciones (undo)

---

### 🔗 Chain of Responsibility (CoR)

Se implementa una cadena de validación para pedidos:

* `ValidadorPedido` (interfaz/base)
* `ValidadorCredito`
* `ValidadorMonto`
* `ValidadorStock`

**Flujo:**
Cada validador decide si:

* ✔ pasa al siguiente
* ❌ detiene la cadena

---

## 🏗️ Estructura del proyecto

```bash
src/main/java/com/universidad/pedidos/
│
├── command/   → patrón Command (acciones y undo)
├── cor/       → cadena de validación (CoR)
├── modelo/    → entidad Pedido
└── PedidosApp.java → punto de entrada
```

---

## ⚙️ Tecnologías utilizadas

* Java 21
* Spring Boot 3.2.0
* Maven
* JUnit 5

---

## 🚀 Ejecución del proyecto

1. Clonar repositorio:

```bash
git clone https://github.com/tu-usuario/tu-repo.git
```

2. Compilar:

```bash
.\mvnw clean install
```

3. Ejecutar:

```bash
.\mvnw spring-boot:run
```

---

## 🧪 Pruebas

Se implementaron pruebas unitarias para:

* ✔ Aplicación de descuentos con Command
* ✔ Funcionalidad de *undo*
* ✔ Validaciones en cadena (CoR)

Ejecutar tests:

```bash
.\mvnw test
```

---

## 📸 Evidencias
<img width="1080" height="761" alt="image" src="https://github.com/user-attachments/assets/771db9e0-2f12-460e-a22f-8d496d54af1b" />

<img width="1085" height="897" alt="image" src="https://github.com/user-attachments/assets/c7aa4fe3-a378-4bcb-a22c-0ae3a6a9366a" />

---

## 📊 Ejemplo de flujo

1. Se crea un pedido
2. Se aplica descuento (Command)
3. Se valida mediante cadena (CoR)
4. Se puede deshacer la operación

---

## ✅ Conclusión

Se implementó un sistema flexible que permite:

* Extender nuevas acciones sin modificar código existente
* Agregar nuevas validaciones fácilmente
* Mantener un flujo limpio y desacoplado

---

## 👩‍💻 Autor

Proyecto académico - Ingeniería de Sistemas
