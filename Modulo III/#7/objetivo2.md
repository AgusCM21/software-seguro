# Objetivo 2: Análisis de Manipulación Transaccional (Cantidades Negativas)

### Analiza el siguiente escenario teórico: Un e-commerce permite agregar productos al carrito. Al interceptar la petición, cambias la cantidad del producto de 1 a -5. El servidor lo procesa y el total del carrito se vuelve un número negativo, lo que termina sumando saldo a tu cuenta en lugar de cobrarte. Explica técnicamente por qué ocurre esta falla y cómo debería el desarrollador validar estrictamente este campo del lado del servidor para evitarlo.

-El servidor acepta una cantidad negativa enviada por el cliente sin validar su signo ni su rango, provocando que el cálculo del total resulte negativo y que la lógica de liquidación o saldo acredite dinero en lugar de realizar un cobro, al haberse omitido la validación estricta del lado del servidor.

-El backend debe validar estrictamente que la cantidad sea un entero positivo dentro de los límites permitidos, rechazar valores inválidos, calcular los importes con precios autoritativos del servidor y garantizar que el flujo de compra exija un total positivo y debite fondos en lugar de acreditar saldo.
